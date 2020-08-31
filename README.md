# Global population analysis

Collection of analysis and database for countries population values overtime. Acros multiples notebooks and python functions were created a MongoDB database and data treatment based on world population data bases.

## World data
A Mongo database was set-up. it is store at an Atlas server:
 - Project: World population
 - Database: world_population
 - Main collections: countries_pop

Main source was taken from United Nations source ([link](https://population.un.org/wpp/Download/Standard/Population/)), a history per country, region, continent and other divisions is displayed at the UN databases. They split into female and male population over time since 1950 until 2100.
Some details about the UN file:
- CSV files are encoded in UTF-8 
- From 2020 (current year) they provide statistical aproximation for population growth [^first]
-  CSV files have the following columns:
    - LocID (numeric): numeric code for the location; for countries and areas, it follows the ISO 3166-1 numeric standard
    - Location (string): name of the region, subregion, country or area
    - VarID (numeric): numeric code for the variant
    - Variant (string): projection variant name (Medium is the most used); for more information see Definition of projection variants
    - Time (string): label identifying the single year (e.g. 1950) or the period of the data (e.g. 1950-1955)
    - MidPeriod (numeric): numeric value identifying the mid period of the data, with the decimal representing the month (e.g. 1950.5 for July 1950)


[^first]: Variant type with provide with several codes () to represent growth over time (check [source](https://population.un.org/wpp/Download/Standard/CSV/))

## Data analysis and data api
The main idea is to use jupyter notebooks to interact witht the MongoDB data by a mongo-client. Data request will be display in the form of plots and interactives graphs.

Futher developments will allow to integrate a short api/library to request for a country population at a given year.

Dillinger is a cloud-enabled, mobile-ready, offline-storage, AngularJS powered HTML5 Markdown editor.

  - Type some Markdown on the left
  - See HTML in the right
  - Magic

## Required libraries
All libraries and require packages all listed inside requirements.yalm file. But, we should not forget to have a special atention to install the MongoDB client

Recover and install environement as:
```sh
> conda env create -f environment.yaml --force
```

Or install only MongoDB client for python as:
```sh
> pip install pymongo
```

Don't forget to update environment.yaml file if new packages were installed:
```sh
> conda env export -n ds_gp -f environment.yaml
```

## To do:
 - Write more Tests
 - Add an interface with Django

License
----
MIT