# open-data

LA Metro Open Data - what's available and where can I find it?  While have no official "Open Data Portal", there is some data out there.  Our [Developer Site](https://developer.metro.net) is the de facto aggregator at the moment.  These are the broad categories of data we currently have available:

* Bus and rail schedules in GTFS format
* Real Time API that pulls data from NextBus and includes an undocumented station parking data.
* Geospatial data
  * Bus/rail lines
  * Bus/rail stops and stations
  * Metro's right-of-way
  * Bike Share Data
  * LA County Bikeways
  * Ridership

## Mission

Government should release machine readable data openly for the public to use, by default.  Doing so benefits both the public and government itself.  Open data that is released should be:

* Machine readable
* Open and free to use
* Detailed enough to be useful
* Given context so it can be used appropriately
* Updated frequently
* Part of a larger public engagement and education effort

## Ideas

### Bikes

* Find the direct source for bikeways data.  Might be multiple separately maintained datasets (Metro, [LA County Public Works](https://egis-lacounty.hub.arcgis.com/datasets/la-county-bikeways).
* Bike Map from metro.net: https://media.metro.net/dcr/bikemap/metro_bikemap.html
* Find who owns these survey results: https://metro.cvent.com/surveys/Questions/SurveyMain.aspx?r=44b4b00d-dfe1-4754-9a2e-a53a9354d68c&ma=0

### Equity

Contact: Naomi Iwasaki (Office of Race & Equity)

Equity Focused Communities Map/Data:
https://www.arcgis.com/home/webmap/viewer.html?webmap=e2b8b6597bcd4db9a1c47737595de070&extent=-119.1491,33.6991,-117.184,34.6794

### APIs

* Better documentation.
* Fix bugs, create better issue notifications.
* Prepare for release of GTFS-RT.

### GIS - OneMAP

Figure out how we can combine our work with what's being done on OneMAP (contacts: Anika and Kenneth)

OneMap Hub for employee guides on how to use ArcGIS:
https://la-metro-onemap-program-lametro.hub.arcgis.com/

ArcGIS Online uses Metro SSO:
https://lametro.maps.arcgis.com/home/index.html

Not sure what this is, but I believe it's only accessible from the Metro internal network:
https://gis.metro.net/portal/

### Operations

Contact: Dan Nguyen

#### Ridership

The [Ridership Stats Dashboard](https://isotp.metro.net/MetroRidership/) and its underlying data is open to our team for re-writing and re-designing.  It's built on .NET/VB and there is no staff in Operations available/knowledgable enough to continue development in its current form.  It is in dire need of improvements to its interface and the ability to download the raw data.

References from other agencies:
* MBTA: https://mbtabackontrack.com/performance/#/detail/ridership/2021-05-01////
* CTA: https://www.transitchicago.com/ridership/#open
* NY Times: https://www.nytimes.com/interactive/2021/03/08/climate/nyc-transit-covid.html

#### Bus/Rail Shapefiles

* Update the line descriptions.
* Confirm if the data includes the Gold Line shuttle (should be mentioned in description).
* Updated headways spreadsheet.
* Rail track shapefiles - broken up by segments between stops?
* Get current shapefile that contains all the rail lines.
* Get current shapefile for rail portals.
* Any single shapefiles that contain all bus lines?
* Provide shapefile data in additional formats (WKT, GEOJSON) and track their usage.

#### Other

* Divisions and their locations. 
* Contextual information about: directly operated vs non-directly operated lines, passenger miles, revenue service hours (RSH), schedule day types, hardware/software systems (HASTUS, APC, ATMS, etc.).
* Operational KPIs beyond ridership stats data.

### Projects/Programs

Talk to Ana Vallianatos for contacts.

* [Program Management Dashboard](https://mtadash.mlmprojectservices.com/) (Program Management contact - Julie Owen)
* Contracts

### Financial

Talk to Ana Vallianatos for contacts.

* Budgets
* Local Return Money Data (OMB contact: Drew Phillips)
  * Last contact: Email to Drew on 6/10/21. Next steps were to have OMB demo the new database they've set up. OMB is interested in making this data public but will need to clear it by a committee and the Board first.

### GTFS

Automate and possibly move/restructure.

The current process for updating GTFS bus data:

Rollin Baker uploads a zip file of the new GTFS data to Google Drive.  He then uses the Google Drive share feature to email the files to a list that he maintains:

> amanda.pacheco@goswift.ly; Baker, Rollin <BAKERRO@metro.net>; bingmapstransit@microsoft.com; chloe.haines@itoworld.com; crivera@devsar.com; data@transitapp.com; drew@interline.io; emma.bridgeford@itoworld.com; fiona_mcdonnell2@apple.com; g.genna@goswift.ly; gabriella@moovit.com; Gordon, John <GordonJ@metro.net>; ian@interline.io; jacob.whitbeck@pactera.com; jacob.whitbeck@pacteraedge.com; justine.coates@microsoft.com; kayla@goswift.ly; Lam, Lan-Chi <LAML@metro.net>; maps_data_validation@apple.com; Martinez, Al <MartinezAl@metro.net>; mgridley@apple.com; michael.jacklin@itoworld.com; moovitaccess@moovit.com; Nguyen, Dan <NguyenD@metro.net>; nicolas@transit.app; pavel.belsky@moovit.com; rob.gaffney@goswift.ly; shane.reynolds@itoworld.com; Simpson, Joe <SimpsonJ@metro.net>; support@goswift.ly; transit_contact@group.apple.com; Wang, Peishan <WANGP@metro.net>; yochi.danino@moovit.com

He includes a brief high level description of changes to the GTFS.  Our web team receives this email notification of the new GTFS data.

Originally, we would have to process it to convert the Windows-style line endings to Unix-style.  It would then be published to the GitLab repository as individual unzipped files in addition to the zip file.  The README file would be updated with the description of the latest changes as well as a log of the zip file contents.

Because of the OpenTripPlanner implementation on metro.net, we would have to publish the new GTFS to GitLab at a specific time - Saturday evening - so that it wouldn't be used by OTP too soon.  That's because the new GTFS' calendar dates don't start until the day of the shakeup and we don't release a merged version of the old and new GTFS (because it was too big for Google to consume back in the day).

Now, because we don't have OTP on our website anymore, some of these things do not apply and we can re-do the way we publish our GTFS.

#### Restructure

1) It is on GitHub instead of GitLab.
2) It archives old GTFS versions.
3) It can be released well in advance before service goes into effect.
4) Build in automation (see below)

This will require us to communicate with data consumers as external stakeholders.  Internal stakeholders to include are Dan Nguyen and Rollin Baker.

#### Automate

The way GTFS gets published currently:

- Rail GTFS updates are automated through a python script that runs nightly by ITS.  This has to do with the fact that the process to generate the GTFS files (coming from HASTUS) results in the files being put into an FTP location that only ITS has access to.  We may be able to request access to, it's uncertain whether we can SSH to it.  This is what we need to ask ITS about.
- Bus GTFS is manual but we should build out an automated workflow.

Normally, bus GTFS updates very infrequently, but starting the week of 9/13, new `calendar_dates.txt` files will be generated weekly.

This file has 2 components.  The base data, which is generated from HASTUS, and the Dodger Stadium/SoFi Stadium service which is NOT in HASTUS and is manually created by Rollin Baker.  The two datasets can easily be appended.  We can also choose to optimize the data by removing non-relevant date ranges.

The thought is:

- We take the existing python script used for rail and create one for the bus GTFS.
- We give that script to ITS to run weekly after the new `calendar_dates.txt` file is generated.
- QUESTION: Do we want ITS to append the two datasets to create the final `calendar_dates.txt`, or do we want our script to do that.

#### Long Term Maintenance Goals

- [ ] We need to know what Rollin does to process the GTFS.
- [ ] We need to work with ITS to figure out how to automate things.

### General

* Proactively post the datasets that are most frequently requested via CPRA/FOIA.
* Track data owners and create more automation in the pipeline.
* Add more contextual information, maybe via interviews with subject matter experts posted on the blog.
* Do we need to notify users about updates and new datasets (via RSS feed, email list, blog, or an updates section)?

## User Research Questions

* What format(s) would you want your geospatial files to be in?
* What data would you want to see?
* Is there an open data platform you have been particularly impressed by?
* Is there something specific you want to accomplish using Metro data?
