# Guarding US

<img src="https://raw.githubusercontent.com/AdrianRdz23/GuardingUS_Homepage/main/Assets/Guarding US-logos.jpeg"/>


## What is Guarding US?

Guarding US is a web application that contains security functions in order to protect residents in a private subdivision. Una de las metas de esta aplicacion es que en cada private subdivision este satisfecho con las funciones necesarias que tiene esta aplicacion. This project is being carried out since I have seen security guards of the private subdivisions of my city are using notebooks to write down the visitors' information.

# Overview

## Key Features

#### Administrators:
- Administrating Catalogs: Roles, Users, and Homes
- Send Notifications to Residents
- Exits and Entrances History
#### Security Guards:
- Administrating Catalogs: Roles, Users, and Homes
- Send Notifications to Residents
- Exits and Entrances History
#### Residents:
- See his/her notifications

<br>

----------------------


# Design Diagrams

## Physical Architecture

<div align="center">
    <img src='https://raw.githubusercontent.com/AdrianRdz23/GuardingUS_Homepage/main/Assets/PhysicalArchitecture.png' width=480>


To be able to use the web application you need a computer/laptop and an internet service. It is recommended that the application be used in Google Chrome. In the second stage of this project, it will also be able to be used with a mobile device, starting with Android devices.
    
</div>

## Logical Flow Chart

<div align="center">
    <img src='https://raw.githubusercontent.com/AdrianRdz23/GuardingUS_Homepage/main/Assets/logical.png' width=480>

This flow chart demonstrates how the app works once you have an account and can log in.
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


</div>

##

<br>

## Sitemap

<div align="center">
    <img src='https://raw.githubusercontent.com/AdrianRdz23/GuardingUS_Homepage/main/Assets/Sitemap.png' width=480>

Sitemap of Guarding US
</div>

##



# Code Snippets


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
This function is about notifications when an administrator or a security guard sends a message to the resident. You have two options: select the residents you want to send a notification or send it to everyone.
</div>
<br>

------------

<br>

##

## Add a Visitor 

```csharp
        //Action to go to add entrance View
        public IActionResult AddEntranceView()
        {

            List<String> addresslist = new List<String>();

            //Get all the addresses of the home table (non-repeatable names of the address)
            foreach (var address in _context.Home.GroupBy(p => p.address).Select(p => new { address = p.Key }).ToArray())
            {
                addresslist.Add(address.address);
            }



            ViewBag.ListofHome = addresslist;

            return View();
        }
```

<div align="center">
In this function it sends the view where the security guard will add visitor information that comes to enter the private subdivision. In addition to entering the view, we also bring a list of addresses to be able to choose with a dropdownlist which address is where the visitor will go.
</div>
<br>

------------

<br>
##

# Software Demo Video

https://youtu.be/g5FPy2DM95k

<br>

##

# Extra Documents

<a href="https://github.com/AdrianRdz23/GuardingUS_Homepage/blob/main/Assets/ProjectProposalGuardingUS.docx?raw=true" download>Project_Proposal.docx</a>

<a href="https://github.com/AdrianRdz23/GuardingUS_Homepage/blob/main/Assets/ProjectRequirements.docx?raw=true" download>Project_Requirements.docx</a>

<a href="https://github.com/AdrianRdz23/GuardingUS_Homepage/blob/main/Assets/ProjectDesignGuardingUS.docx?raw=true" download>Project_Design.docx</a>


<br>

# Credits/Links
Technologies/Software of Guarding US:

[Visual Studio](https://visualstudio.microsoft.com "Visual Studio")

[Microsoft IIS Server](https://www.iis.net "Microsoft IIS Server")

[Microsoft SQL Server](https://www.microsoft.com/en-us/sql-server/sql-server-2019 "Microsoft SQL Server")



