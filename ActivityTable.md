# Activity Table

| Activity                  | Task | Task Precedence | Time (Weeks) |
|:--------------------------|:-----|:----------------|:-------------|
| Project Initialization    | A    | none            | .5           |
| __Server__                                                        |
| Database/Model Layer      | B    | A               | .5           |
| Authentication            | C    | B               | 1            |
| Mobile API Implementation | D    | C               | 1            |
| Views/View Controllers    | E    | B               | 2            |
| __iPhone App__                                                    |
| Core Data Setup           | F    | A               | .5           |
| Views/Controllers         | G    | A               | 1            |
| Drink Notifications       | H    | F, G            | 1            |
| Integration With Server   | I    | C, F            | .5           |
| User Authentication       | J    | I               | 1            |
| Synchronization           | K    | J               | 1            |

### Project Initialization

Project initialization involves setting up development environment, creating empty project files, and implementing version control.

### Server

#### Database/Model Layer

This involves creating and connecting to a postgresql database.
After the database is set up all of the model tables will be added and the model classes will be created.

#### Authentication

Authenctication is the process of adding the methods for authenticating/tracking users the user model.

#### Mobile API Implementation

This activity involves making the JSON API the modile apps will use available.

##### Views/View Controllers

During this activity the html/css for the web server will be refined to make it easier for admins to use.

### iPhone App

#### Core Data Setup

For Core Data Setup, the Core Data persistent storage manager will be initialized.
The model classes will be generated and implemented by Core Data.

#### Views/Controllers

During this activity the UI code will be implemented.

#### Drink Notifications

Drink notifications are the notifications that remind the user to drink.
After this step it will be possible to schedule these notifications.

#### Integration With Server

This step involves adding networking capabilities so the app can interact with the server.
The networking code will interact with Core Data to persist the data that is downloaded from the server.

#### User Authenticaiton

User authentication involves using the server integration to interact with the server's authentication capabilities

#### Synchronization

Synchronization involves using the server integration to interact with the server's synchronization capabilities