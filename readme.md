# Admin Dashboard

## About

This project uses the provided SQLite database to access data through API calls.

![](Overview.png)


## Imlementation goals


1. Sending rate per `appID`
  - Distribution of _sending rate within the appID_ (can be selected by the user)
  - Distribution of _average application sending rate_ across all appIDs
2. Sending rate per `buildName`, `buildVer`
  - Distribution of _average sending rate_ for the combination of `buildName` and `buildVer`
~~selected by the user~~ 
3. Media type per `appID` 
  - Distribution of _media types_ with the appID ~~selected by the user~~

The **API** is available at http://localhost:8081

The **app** is available at http://localhost:3000

## API routes
All routes use the GET method. 

`/app`: Return a list of all `appIDs`. 

`/app/:appID`: Return all data for given `appID`. Number of rows differ between appIDs. 

`/app/:appID/:field`: Return all data for given `field` for given `appID`.

`/fields`: Return all table columns. 

**NEW**

`/apps/avg/sendrate`: Return the sending rate of all apps that contains an entry in this field.

`/apps/mediatypes`: Return usage count of all apps' media type. (Media type is 'audio' and/or 'video').

`/browsers/avg/sendrate`: Return average sending rate of all browsers (build and version) that contains an entry in this field.

`/app/:appID/avg/sendrate`: Return an app's average sending rate.

