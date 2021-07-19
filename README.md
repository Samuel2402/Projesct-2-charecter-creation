# Projesct-2-charecter-creation

# fundamental-project-1

## Contents
* [Introduction](#introduction) 
* [Proposal](#proposal)
* [Trello](#trello)
* [Risk Assessment](#risk-assessment)
* [Entity Relationship Diagram](#entity-relationship-diagram)
* [Development](#development)
* [Virtual Machine, GCP, File format](#Virtual-Machine,-GCP,-File-format)
* [Gitignore](#Gitignore)
* [Creating and populating tables](#Creating-and-populating-tables)
* [Forms and HTML](#Forms-and-HTML)
* [Routes](#routes)
* [Frontend](#Frontend)
* [linking Routes and database with frontend](#linking-Routes-and-database-with-frontend)
* [Testing](#testing) 
* [gunicorn](#gunicorn)
* [Jenkins](#jenkins)
* [Known bugs and planned updates](#bugs)


# Introduction
The project included the creation of an application, split into four services - a Server to deliver html and compile information, 2 services to serve information through a simple api using GET requests, and a final service to recieve information from services 2 + 3 to create a new result. 

# Proposal
To create the MVP within the specified time period, the idea specified to meet criteria is a Character Generator, with Routes to generate a characters Race, Class, Blessing, Stats and Points. These will be split into services 2, 3 and 4. Service 1 will compile information from service 2, 3 and 4, present it on HTML, uplaod character to db insance on Mysql, and Query the 10 most recent generated characters.

# Trello
I began the project by listing out all tasks that i believed would need to be completed to meet the MVP - information for this was taken from QA Community to reduce the likelihood of missing an key element and was updated as the project progressed.

![Trello board design](./Images/Trello.jpg)

My trello board was updated as the project developed, however it is still only a simple trello board (utilises a few user stories and MoSCoW prioritisation stratagies). Trello functioned as to-do, doing, and done to clearly demonstrate the projects progress and was comprised of prodominatly crucial stages of operations.

# Risk Assessment
I created a Risk Assesment before beginning my project to highlight potential risks that i have identified. 

![developed design](./Images/Final Risk Management.jpg)

I continued added columns as the project progressed and i found a potential issue, including potential risks related to github secrets, as-live testing and any issues with the project that could cause delays.
Furthermoor risk was updated and whether or not an issue occured to-date.
- I added tools that can be used to mitigate issues to the risk assesment. 

# Entity Relationship Diagram
my entity relationship diagram went through a few iterations as i worked out their relationship and what the contents of each table would be.

![initial design](./Images/)

Initial and final ED for table: 

![initial design](./Images/Tables.jpg)

Initial scope for project:

![initial design](./Images/Projet scope.jpeg)



# Development
The project began with building my tables in python and linking them with a db made in mysql. I created a VM and a MySQL Instance using Google Cloud Provider, Created my db in MySQL, added firewall exceptions, and added permissions for VM to access database. 

## Virtual Machine, GCP, File format
Secondly was downloading and installing necessary software to create and run my app effectively, then creating my file structure with application, app.py, create.py, __init__.py and others necessary for the project to function efficiently and maintain a good level of organisation.

![application tree design](./images/tree-application.jpg)

## Gitignore
Added gitignore and added confidential files such as venv, credentials and pycache to prevent spilling secrets to github.

## Creating and populating tables 
Following the successfull creation and implementation of my VM and its software i created my tables in python and linked my app to my db in MySQL.
After creating my tables i edited my create.py to populate the table with some example information to be used with testing and demonstrations.

## Forms and HTML
Created my forms to gather the information needed through a basic html webpage, with submit buttons and boxes to input information.

## Routes
Created routes for: - Home page
                    - Add Receipt
                    - Read Receipt
                    - Edit Receipt
                    - Delete Receipt

I focused on CRUD functionality for one aspect of my web page - Tracking and keeping receipts. this was to save time and meet the MVP. These routes fufil there purpose with text to appear upon a successful action on Add or Delete.

after CRUD was completed for Receipts i added more routes for Store:
                    - Add Store
                    - Read Stores

- Added basic error messages to my routes to help with inputing relevant information

This is the structure of the current working version - with more pages to be added in a later iteration.

## Frontend
A web layout was created in HTML along with other pages needed to be rendered, and stored in templates to be called by routes. 
Layout was further develouped to be more user freindly including a navigation system for easily moving between pages with standard information.

## linking Routes and database with frontend
Finalised routes with information and added return_render templates.
At this point i was testing the functions of routes:
  - Displaying information
  - Displaying correct information
  - Navigating pages 
  - CRUD functionality on all current HTML pages works as intended.

## Testing
Created a test_app.py to test functionality of routes and created validaors (to be implemented).
Tests cover: 
  - Building database and tables
  - Populating tables
  - Testing Read for all available pages
  - Testing Add for Add Store & Add Receipt

Requires further testing before deployment including
 - Update and Delete tests working
 - Selenium used for integration testing
 - Port testing

Current test coverage

![test coverage](./images/test-coverage.jpg)

Test coverage is currently too low for deployment and needs to be improved.

## Gunicorn 
Was installed and run as intended to test stability. run successfully for a time and website saw no issues with the implemented workers.

![gunicorn](./images/gunicorn.jpeg)

## Jenkins
Jenkins is being utilised to setup and deploy working versions of my app and is working in its current state.
Script was added, with permissions changed to execute and run. After logging in successfully i created my build. Furthermore i had to edit my sudo visudo to add jenkins permissions before it would run successfully

![jenkins working](./images/jenkins1.jpg)

My db instance is used in execute bash shell currently, however my build is behind a secure jenkins login so the risk of a leak is low. (execute line is ommited)

![jenkins bash1 ](./images/jenkins2.jpg)
![jenkins bash2 ](./images/jenkins3.jpg)

Jenkins requires further implementation of webhooks and architecture to save build versions as zip files.

# Bugs 
 - Information entered into decimal feilds is currently tempermental and needs refining
 - Inclusion of drop down Choices for selecting receipts
 - Stats table created and working 
 - Date not entering correctly (shows None)

(to be added as they are discovered)
