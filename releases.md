# Ensembl release cycle

We put out an Ensembl release every 2-3 months. These contain all new data and software updates to Ensembl.

## What's in a release?

A release contains all new updates, including:
* Data:
    * Addition of new datasets, such as new species or new data types.
    * Updates to existing data.
* Interfaces:
    * We may build new web-pages to accomodate new data types, or to improve the visualisation of existing data.
    * We may tweak existing web-pages to display extra data or improve the way it appears to make the data easier to work with.
* Database updates:
    * We may change the underlying structure of the MySQL database, particularly if this is required by new data types. These changes should be invisible to someone using the website, BioMart and the APIs, but if you are accessing Ensembl data via MySQL queries, you may need to check the schema.
    * New endpoints for the REST API to access new or existing data types.
    * Updates to the Perl APIs to provide new methods or modify existing methods.

## What are the benefits?

The major advantage of a release cycle over rolling updates is that all data are traceable. We recommend noting down the release number when you retrieve data from Ensembl. This allows you to access the same version of the data when you follow up later on. It also ensures that all data and software are version matched.

## How do I access previous releases?

### Browser and BioMart

[Archive sites](general_principles/archives.md) are available to allow you to access previous Ensembl browser websites and BioMart.

### Perl APIs

APIs are version matched to releases. This means if you use an API for a previous Ensembl release, it will use the database from the same release. If you want to install an older API, you can do so by [selecting the correct branch from GitHub].

### REST APIs

Currently the REST APIs only access the current database.

### MySQL

You can access previous MySQL databases by using a different database number. Some very old databases are on a [different server]. You may wish to look at the schema in an archive browser site.

### FTP

The flatfiles for Ensembl release 19 onwards are stored on the FTP site.
