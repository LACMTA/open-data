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

`TODO:` Create Issues for these and create a tagging system for categories & priorities.

* Bikes
  * Find the direct source for bikeways data.  Might be multiple separately maintained datasets (Metro, [LA County Public Works](https://egis-lacounty.hub.arcgis.com/datasets/la-county-bikeways).
  * Bike Map from metro.net: https://media.metro.net/dcr/bikemap/metro_bikemap.html
  * Find who owns these survey results: https://metro.cvent.com/surveys/Questions/SurveyMain.aspx?r=44b4b00d-dfe1-4754-9a2e-a53a9354d68c&ma=0
* Ridership
  * More granular/frequent ridership data with relevant context and easy to maintain pipeline.
  * Get downloadable raw data from the Ridership Stats dashboard: https://isotp.metro.net/MetroRidership/
* API
  * Better documentation.
  * Prepare for release of GTFS-RT.
* Bus/Rail
  * Update the line descriptions.
  * Confirm if the data includes the Gold Line shuttle (should be mentioned in description).
  * Updated headways spreadsheet.
  * Rail track shapefiles - broken up by segments between stops?
  * Get current shapefile that contains all the rail lines.
  * Get current shapefile for rail portals.
  * Any single shapefiles that contain all bus lines?
* Operations
  * Divisions and their locations. 
  * Contextual information about: directly operated vs non-directly operated lines, passenger miles, revenue service hours (RSH), schedule day types, hardware/software systems (HASTUS, APC, ATMS, etc.).
* Projects
  * Project management, contract, budget data.
* General
  * Provide shapefile data in additional formats (WKT, GEOJSON) and track their usage.
  * Proactively post the datasets that are most frequently requested via CPRA/FOIA.
  * Track data owners and create more automation in the pipeline.
  * Add more contextual information, maybe via interviews with subject matter experts posted on the blog.
  * Maintain RSS feed for data updates (?)
  * Register users for data updates (?)

## User Research Questions

`TODO:` Create a survey. Track progress of outreach.

* What format(s) would you want your geospatial files to be in?
* What data would you want to see?
* Is there an open data platform you have been particularly impressed by?
* Is there something specific you want to accomplish using Metro data?
