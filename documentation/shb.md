---
layout: project
title:  Studies on Human Behaviour - 2024
permalink: /documentation/shb/
---

# Studies on Human Behaviour - 2024

## Rationale for a new dataset

The data uploaded on the website was collected within the scope of the "Studies of Human Behaviour" exam in the year 2024.
It consists of timed diaries and mobile phone sensors data, acquired from a single person (myself) over the course of 10 days through the LiveMe application.
The raw data was then elaborated and filtered to obtain a selected dataset to perform some basic analysis of factors impacting mood, mood change and answer delay.

## Method

The data was collected through a Fairphone 5G with Android 14 operating version, from 01/10/24 to 10/10/24. The original collection span was supposed to last until 22/10/2024, but after an Android security update the application stopped working and it was not possible to continue.
All sensors were switched on for the whole duration of the collection and all possible authorizations were given to the application.
Timed diaries were sent every half an hour, but not always answered instantly.

## Data Records

All data records consist of parquet files, where each row corresponds to a timestamp in the collecion. The frequency changes based on the dataset. 

#### 2024-Shb-Trento-Airplane Mode Event

Every time the airplane mode is switched on or off, collects a true/false string.

#### 2024-Shb-Trento-Application Event

Every 5 seconds, collects the name of the application running in the foreground.

#### 2024-Shb-Trento-Battery Charge Event

When the phone is under charge or taken off charge, collects a true/false string and the type of charger.

#### 2024-Shb-Trento-Battery Monitoring Log

Every minute collects the level of the battery unless it is 20% or lower.

#### 2024-Shb-Trento-Bluetooth

Every millisecond collects new bluetooth devices in the surroundings, both normal and low-energy.

#### 2024-Shb-Trento-Cellular Network

Every second collects signal strength and type of cell to which the phone cellular network is connected.

#### 2024-Shb-Trento-Doze

When the phone switches on or off battery saving mode, collects a true/false string.

#### 2024-Shb-Trento-Location

Collects gps location, passive location (when an application that uses the location is used), and network location in terms of latitude, longitude, altitude, bearing and speed.

#### 2024-Shb-Trento-Music

When music is played or stopped on the phone, collects a true/false string.

#### 2024-Shb-Trento-Notification

Whenever a notification is received by the phone or dismissed by the user, collect information about the notification.

#### 2024-Shb-Trento-Ring Mode Event

When the phone mode is switched between normal, silent and vibrate, collects a string of the mode being activated.

#### 2024-Shb-Trento-Screen

At milliseconds rate, collects whether the phone screen is on or off through a string.

#### 2024-Shb-Trento-Step Counter Event

Every 100 steps taken from last phone power on, collects the total number of steps.

#### 2024-Shb-Trento-Step Detector Event

Collects an entry for every step taken by the user.

#### 2024-Shb-Trento-Touch

Collects an entry every time the screen is touched.

#### 2024-Shb-Trento-Wifi

Collects ssid, bssid of the wifi cell the phone is connected to and a true/false string

#### 2024-Shb-Trento-Wifi Networks Event

At milliseconds rate, collect informations about all WiFi networks available. 

#### 2024-Shb-Trento-Timediary

Every entry is a time diary or morning/evening question answer. Contains information on when the notification was sent, when it was answered, the time of the notification, whether a break status was on and answer to questions:
- What are you doing?
- Where are you?
- With whom are you?
- What is your mood?
Plus some subquestions conditioned on specific answers.

## Validation

Due to repeated malfunctions of the used application, the dataset is of quite small size and its validity for further analysis is dubious.

The following table reports the number of entries for every sensor.

|sensor|entries||sensor|entries|
|---|---|---|---|---|
|airplane mode|2||music|1261|
|applications|110096||notification|19972|
|battery charge|421||ring mode|51|
|battery level|9140||screen|11136|
|bluetooth_0|343750||step counter|36310|
|bluetooth_1|343751||step detector|69670|
|cellular network|3885||touch|390727|
|doze|56||wifi|21|
|location|106840||wifi networks|19644|

In some cases the low number is due to the event type of the collection, in other cases it is plausisble that some issues with the sensor has occurred, even if no systematic missing can be identified.

The following table consists in a first broad analysis of the completeness for active data.

|type|total|answered|missing|completeness|
|---|---|---|---|---|
|survey|1|0|1|0|
|morning questions|8|8|0|1|
|evening questions|9|9|0|1|
|time diaries|414|306|108|0.74|

The survey has been answered by the user but the answer has not been uploaded on the application due to the security update that stopped the data collection.
Time diaries missings have further been analysed. 30 of them have not been answered because of breaks in the applications. 73 of them are expired and correspond to time diaries sent during the night, but the application option for activating a break malfunctioned. Finally, 5 of them were answered only after the security update and were not registered in the application.

When attempting to perform further analysis, the expired questions and the breaks during sleep were discarded, while one break during sport activities and one break during class was imputated according to answers typical during other sport activities and class moments.

## Conclusion and comments

This section outlines the final considerations of the project, observations, and limitations of the work. If you want, you can include feedback about the project.

Examples:

- Which analysis would you like to perform on this data (e.g., investigate which activities during the day impacted your mood in the evening)?
- Which other types of data would you like to collect or produce to perform the analysis?

- What and why would you change in the data collection design to increase the quality of the dataset? (e.g, additional sensors, more/less questions, shorter data collection period)


## Information about this template

### Useful references

This template is an adaptation of these guidelines on how research datasets are described:

- [IMWUT Dataset Papers](https://dl.acm.org/journal/imwut/dataset-papers-guidelines)
- [Scientific Data - Nature](https://www.nature.com/sdata/publish/for-authors)

Dataset paper example: [GLOBEM: Cross-Dataset Generalization of Longitudinal Human Behavior Modeling](https://dl.acm.org/doi/pdf/10.1145/3569485)

### Technical details about this webpage
This document is written in Mardown. [Here](https://www.markdownguide.org/basic-syntax/) you can find the basic syntax. Once saved, GitHub automatically converts this file into a html page.
