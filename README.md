# Guarding US

<img src="https://raw.githubusercontent.com/AdrianRdz23/GuardingUS_Homepage/main/Assets/Guarding US-logos.jpeg"/>


## What is Guarding US?

Guarding US is a web application that contains security functions in order to protect residents in a private subdivision. Una de las metas de esta aplicacion es que en cada private subdivision este satisfecho con las funciones necesarias que tiene esta aplicacion. This project is being carried out since I have seen security guards of the private subdivisions of my city are using notebooks to write down the visitors' information.

# Overview

## Key Features

#### Administrators:
-Administrating Catalogs: Roles, Users, and Homes
-Send Notifications to Residents
-Exits and Entrances History
#### Security Guards:
-Administrating Catalogs: Roles, Users, and Homes
-Send Notifications to Residents
-Exits and Entrances History
#### Residents:
-See his/her notifications

<br>

----------------------


# Design Diagrams

## Physical Architecture

<div align="center">
    <img src='https://raw.githubusercontent.com/collinwillis/GuardingUS_Homepage/main/Assets/PhysicalArchitecture.png' width=480>


Para poder usar la web aplication se necesita una computadora/laptop y un internet service. Es recomendable que la aplicacion se use en Google Chrome. En la segunda etapa de este proyecto, tambien se va a poder usar con un dispositivo movil, empezando con los dispositivos Android.
</div>

## Logical Flow Chart

<div align="center">
    <img src='https://raw.githubusercontent.com/collinwillis/GuardingUS_Homepage/main/Assets/logical.png' width=480>

This diagram shows the flow of the possible ways a user could interact with the application. This is not a sitemap.
En este flow chart se demuestra en como funciona la aplicacion una vez que tengas una account y puedas iniciar sesion.
</div>


##

<br>

## API Design

<div align="center">
    <img src='https://raw.githubusercontent.com/collinwillis/GuardingUS_Homepage/main/Assets/APIdesign.png' width=480>

This is a sitemap for Steepl. This diagram shows all pages in the app and how they are connected to each other.
This image is an API Design
</div>



##

<br>

## UML Design Diagram

<div align="center">
    <img src='https://raw.githubusercontent.com/collinwillis/GuardingUS_Homepage/main/Assets/er_diagram.png' width=480>

Steepl uses a NoSQL firestore database. This diagram shows the database collections' and subcollections' structure.
Guarding US usa a MYSQL database con un total de seis tables, por el momento.
</div>

##

<br>

## Youtube Video Detail Retrieval Diagram
#### <a href="https://raw.githubusercontent.com/collinwillis/Steepl_Homepage/main/Assets/video_diagram1.png?raw=true">Diagram Link</a>
<div align="center">
    <img src='https://raw.githubusercontent.com/collinwillis/Steepl_Homepage/main/Assets/video_diagram1.png' width=480>

This diagram demonstrates the method behind how Youtube videos and their properties like title, thumbnail, creator, etc. are interacted with by the Steepl application. 
Firebase stores a Youtube video ID and that is used with the Youtube Data API to return required data about the video’s properties. When a video is clicked the Steepl application will open the Youtube application on the user’s device by combining a YouTube URL with the ID to open the clicked video.

</div>

##

<br>

# Code Snippits


##

## IActionResult Function to Select the resident(s) to send a Notification

<div align="center">
This function takes in the video IDs from the database, fetches the video details for each ID via the YouTube Data API, and stores the retrieved data in JSON format in a returned array.
</div>
<br>

------------

<br>

##

## Add a Visitor Function

<div align="center">
This function is called when the user selects a mood from the "How Are You Feeling" options (moods). This function retrieves a set quantity of each content type (verses, videos, and testimonies) from each topic that has the same scale level as the mood selected. The retrieved content is randomized and then returned.
</div>
<br>

------------

<br>

##

# Downloadable Documents



<br>
<br>

# Diagram Image Links



<br>
<br>

# Credits/Links
Technologies/Software that power Steepl:

[React Native](https://github.com/facebook/react-native "React Native")

[Redux Toolkit](https://github.com/reduxjs/redux-toolkit "Redux Toolkit")

[Youtube Data API](https://developers.google.com/youtube/v3 "Youtube Data API")

[Firebase](https://firebase.google.com/ "Firebase")



