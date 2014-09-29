# CSC 4501 Meeting 1

28 September 2014 at CC's Coffee House on Burbank

- Jonathan Hooper
- Cody Rogers
- Kon-Kon Chao

## Agenda

1. Group Merger Dynamics
2. TapWater System Architecture
3. Group Roles
4. Github
5. Plans For Next Meeting

## 1. Group Merger Dynamics

Since both of our groups contain only 2 people and the class demands groups of 3-5, we have decided to merge our groups to form a group of 4.
We discussed which project we will pursue and agreed that we will work on the TapWater project together.

## 2. TapWater System Architecture

### Requirements

The TapWater application has the following requirements:

1. __Tracking Drinks of Water:__ Users should be able to input the amount of water they drink as they drink it throughout the day.
2. __Displaying Drink History:__ Users should be able to see how many drinks they have had on the current day as well as the amount of time since their last drink. In addition, they should be able to go back and see drinks from previous days.
3. __Authentication and Identification:__ Users should be able to log in/out of the application to identify themselves. The application should still be usable without authenticating.
4. __Syncing Drink History:__ Authenticated users must be able to access their drink history from any device they are logged in on.
5. __Scheduling Drink Notifications:__ Users should be able to select a time frame (e.g. 9:00 AM to 10:00 PM) and a target goal for how much water to drink. They should then receive notifications reminding them to drink a glass of water at even intervals throughout the day.

### Components

To meet the requirements listed above, TapWater will be created from the following components.

#### Server

TapWater will feature a centralized server. It will serve as a data service for the other components.

The server will feature an API with the following capabilities:

1. Creating and authenticating users
2. Saving drinks associated with an authenticated user
3. Downloading an authenticated user's drink history

We have decided that the server will be built in Ruby with the Ruby on Rails web framework.
For the purposes of this class we plan on hosting the server for free on Heroku.

#### Mobile Applications

<img src="https://raw.githubusercontent.com/TapWater/TapWater-Docs/master/Screenshots/prototype01.png" align="left" width="250px">
<img src="https://raw.githubusercontent.com/TapWater/TapWater-Docs/master/Screenshots/prototype02.png" align="left" width="250px">

<br />

TapWater will feature an iOS and Android application.
The applications will be as similar in form and function as their platforms will allow.
The mobile applications are the components that users will interact with directly.

The mobile applications will have a model layer that will mimic the model layer on the server.
This includes drinks and users with whom drinks are associated.

In addition to the model layer, the mobile applications will have the following Views/View Controllers:

1. __Home Screen:__ The home screen will provide an interface for logging drinks. It will have 3 buttons, each corresponding to an amount of water (4oz, 8oz, 16oz). In addition, it will show the user how many drinks they have had that day and how long it has been since their last drink.
2. __Drink History Screen:__ The drink history screen will show the user the list of drinks they have had in the past segmented by date. The drinks will be listed in a table view with information such as what time it was when the drink was logged and what kind of drink it was. Users will also be able to use this screen to delete duplicate or accidental drinks.
3. __Drink Notification Schedule Screen:__ This screen allows users to schedule notifications to remind them to drink water. The users will set a goal for the number of drinks they want to drink. Then they will select a beginning/end time from within the 24 hour day. After this, the user can enable/disable notifications to receive reminders to drink water at even intervals throughout the day.
4. __Profile Screen:__ This screen allows users to sign up or sign in to their account. If they are already signed in, it gives them the option to sign out. Accounts are not necessary to use the application but they are needed to enable synchronization.

The iOS application will be built in Swift with the iOS SDK. The Android application will be built in Java with the Android SDK

## 3. Group Roles

### Jonathan Hooper

1. Work on the Rails server
2. Work on the iOS Application

### Cody Rogers

1. Work on the Android Application

### Kon-Kon Chao

1. Work on the Rails server
2. Work on the iOS Application

## 4. Github

We have created a Github organization to use throughout the duration of the project.
It can be found at [https://github.com/TapWater/](https://github.com/TapWater/)

We created 4 repositories for the project.

- __[TapWater-Rails](https://github.com/TapWater/TapWater-Rails)__ for the server
- __[TapWater-iOS](https://github.com/TapWater/TapWater-iOS)__ for the iOS application
- __[TapWater-Android](https://github.com/TapWater/TapWater-Android)__ for the Android application
- __[TapWater-Docs](https://github.com/TapWater/TapWater-Docs)__ for consolidating project documentation

## 5. Tasks For Next Meeting

We plan to do the following between now and then next meeting

- Kon-Kon will install Ruby on Rails
- Cody will create a task breakdown for the Android App
- Jonathan will create a task breakdown for the Rails/iOS App

At the next meeting we plan on doing the following:

- Catch up on how development is going and make sure everyone is on track
- Use the task breakdowns that Jonathan and Cody produced to create a project-wide task list and Critical Path Diagram/Gantt Chart
