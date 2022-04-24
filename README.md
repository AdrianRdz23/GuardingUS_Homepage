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
    <img src='https://raw.githubusercontent.com/AdrianRdz23/GuardingUS_Homepage/main/Assets/PhysicalArchitecture.png' width=480>


Para poder usar la web aplication se necesita una computadora/laptop y un internet service. Es recomendable que la aplicacion se use en Google Chrome. En la segunda etapa de este proyecto, tambien se va a poder usar con un dispositivo movil, empezando con los dispositivos Android.
</div>

## Logical Flow Chart

<div align="center">
    <img src='https://raw.githubusercontent.com/AdrianRdz23/GuardingUS_Homepage/main/Assets/logical.png' width=480>

This diagram shows the flow of the possible ways a user could interact with the application. This is not a sitemap.
En este flow chart se demuestra en como funciona la aplicacion una vez que tengas una account y puedas iniciar sesion.
</div>


##

<br>

## API Design

<div align="center">
    <img src='https://raw.githubusercontent.com/AdrianRdz23/GuardingUS_Homepage/main/Assets/APIdesign.png' width=480>

This image is an API Design of Guarding US
</div>



##

<br>

## UML Design Diagram

<div align="center">
    <img src='https://raw.githubusercontent.com/AdrianRdz23/GuardingUS_Homepage/main/Assets/uml.png' width=480>

Steepl uses a NoSQL firestore database. This diagram shows the database collections' and subcollections' structure.
Guarding US usa a MYSQL database con un total de seis tables, por el momento.
</div>

##

<br>

## Sitemap

<div align="center">
    <img src='https://raw.githubusercontent.com/AdrianRdz23/GuardingUS_Homepage/main/Assets/Sitemao.png' width=480>

Sitemap of Guarding US
</div>

##



# Code Snippits


##

## IActionResult Function to Select the resident(s) to send a Notification

```csharp
        public IActionResult SendNotificationProcess(UserNotificationListViewModel userNotificationListViewModel)
        {

            // step 3 - not visible to the user.  Background process.
            // process each checked user.  Add a notification to the db.
            if (Request.Form["action"] == "Send")
            {
                SecurityGuardDAO guardDAO = new SecurityGuardDAO();

                foreach (var user in userNotificationListViewModel.NotificationsList)
                {
                    if (user.notification.IsSelected == true)
                    {
                        //Apply the method to send a user the notification on the database
                        guardDAO.SendUser(user);
                    }
                }
            }
            else if (Request.Form["action"] == "Send Everyone")
            {
                SecurityGuardDAO guardDAO = new SecurityGuardDAO();

                foreach (var user in userNotificationListViewModel.NotificationsList)
                {
                    //Apply the method to send a user the notification on the database
                    guardDAO.SendUser(user);
                }
            }
            return View("SecurityGuardView");
        }
```

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
Technologies/Software of Guarding US:



