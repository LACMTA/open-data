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
