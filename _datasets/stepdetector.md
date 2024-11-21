---
schema: liveme
title: 2024-Shb-Trento-Step Detector Event
organization: liveme organization  # Copyright Holders in the config file
notes: Android API that counts (incrementally) the number of steps since the devices booted. The step detector sensor collects an event each time a step is taken by the user. The value reported by the sensor is always one, the fractional part being always zero, and the event timestamp is the time when the user’s foot hit the ground. 
resources:
    - name: codebook
      # URL must link to the corresponding codebook
      url: >-
          /liveme/documentation/codebooks/stepdetector.html
      format: html
    - name: project description
      url: >-
          /liveme/documentation/shb
      format: html
    - name: Datascientia community project
      url: >-
          https://ds.datascientia.eu/community/public/projects/63cd43b5-9e20-4f36-a6b6-275946352522
      format: html
license: 'https://datascientiafoundation.github.io/LivePeople/resources/2023LivePeopleLicense.html'  # Fixed field

dataset_name: Stepdetector
location: Trento (IT)
latitude_map: 46.04
longitude_map: 11.07
start_date: 2024-09-24T00:00
end_date: 2024-10-24T00:00
dataset_type: Sensors
sensor_type: Motion
size: 0,43 MB
dataset_format: parquet  # Fixed
data_origin: direct observation
number_participants: 1
language: unknown
collection_name: SHB course
project_url: <a href="https://ds.datascientia.eu/community/public/projects/63cd43b5-9e20-4f36-a6b6-275946352522">Datascientia community project</a>
5_stars: 3  # Fixed value
publication_date: 2024-11-03 14:05:28  # Current timestamp
identifier: 007.AAAO.AAA.BI  # Generated based on the defined rules
request_contact: datadistribution.knowdive@unitn.it
maintainer: name  # Maintainer based on authors
maintainer_email: datadistribution [DOT] knowdive [AT] unitn [DOT] it  # Fixed email
category:
  - Personal data
type:
  - Datasets
---