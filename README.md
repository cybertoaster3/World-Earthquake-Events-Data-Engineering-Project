# World-Earthquake-Events-Data-Engineering-Project

## Project Overview
An end-to-end data engineering pipeline built with Microsoft Fabric to ingest, transform, enrich, and prepare earthquake event data for analytical use.

Earthquake event data is sourced from [USGS](https://earthquake.usgs.gov/).

The project follows a Medallion Architecture, with the Gold layer serving as a curated analytical data mart for downstream reporting and analysis.

Technologies Used: Python, PySpark, Microsoft Fabric, Fabric Lakehouse

## Getting Started
This project was developed and executed in Microsoft Fabric. The notebooks require a Microsoft Fabric workspace with a Lakehouse attached. 

To run the project:

  1. Import the notebooks into a Microsoft Fabric workspace.
  2. Attach the notebooks to the project Lakehouse.
  3. Set up the Fabric Data Factory pipeline.
  4. Run the pipeline to execute the Bronze → Silver → Gold workflow.

The pipeline automates the movement of data through each layer rather than requiring the notebooks to be executed manually.

## Repository Contents
`01 World Earthquake Events API - Bronze Notebook`: Ingests earthquake event data from the USGS API and stores the raw JSON data in the Fabric Lakehouse.

`02 World Earthquake Events API - Silver Notebook`: Cleans, transforms and consolidates the raw data into a structured dataset.

`03 World Earthquake Events API - Gold Notebook`: Refines the Silver data to create a business-ready dataset. The resulting `earthquake_events_gold` table acts as the analytical data mart, ready for downstream analysis and BI reporting.

## Data Attribute Definitions
`id`: A string identifier for each data record.

`latitude`: The latitude of the event, stored as a double.

`longitude`: The longitude of the event, also stored as a double.

`elevation`: The elevation at which the event occurred, expressed in meters, stored as a double.

`title`: A string representing the title or name of the event.

`place_description`: A string describing the location of the event.

`sig`: A bigint (large integer) representing the significance score of the event.

`mag`: A double indicating the magnitude of the earthquake.

`magType`: A string describing the type of magnitude scale used.

`time`: A timestamp marking the exact time of the event.

`updated`: A timestamp indicating the last update time for the event data.

## Prerequisites
- Microsoft Fabric Account.
- Fabric Administrator (or access to individual with Admin account).
