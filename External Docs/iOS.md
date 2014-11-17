# AppDelegate

The AppDelegate is responsible for responding to events above the scoper of the application.
The AppDelegate also initializes and manages the Core Data Stack.

### application(_, didFinishLaunchingWithOptions:)

```swift
func application(application: UIApplication!, didFinishLaunchingWithOptions launchOptions: NSDictionary!) -> Bool
```

### applicationWillTerminate(application:)

```swift
func applicationWillTerminate(application: UIApplication!)
```

The UIApplicationDelegate method that is called when the application finishes launching

# Drink

The Drink class represent a drink object.

## Properties

- drinkDate (_NSDate_): The date the drink was created
- uuid (_String_): A globally unique identifier for the drink
- category (_NSNumber_): The integer key for the DrinkCategory of the drink
- removed (_NSNumber_): Whether or not the drink has been removed from the database
- user (_User_): The user the drink belongs to

## Class Methods

### insertDrinkWithCategory(_, drinkDate:, user:) 

```swift
class func insertDrinkWithCategory(category: DrinkCategory, drinkDate: NSDate, user: User) -> Drink
```

The primary factory method for a drink.
This method creates a drink and inserts it into the database.

##### Parameters

- category: The drink's category
- drinkDate: The drink's drinkDate
- user: The drink's user

##### Return

A Drink object with the specified parameters

### newDrink()

```swift
class func newDrink() -> Drink
```

The factory method for a drink with the category Drink.
This method creates the drink with the drink date set to the current date and the user set to the current user.

##### Return

A new drink object with the category set to Drink

### newGlass()

```swift
class func newGlass() -> Drink
```

The factory method for a drink with the category Glass.
This method creates the drink with the drink date set to the current date and the user set to the current user.

##### Return

A new drink object with the category set to Glass

### newBottle() 

```swift
class func newBottle() -> Drink
```

The factory method for a drink with the category Bottle.
This method creates the drink with the drink date set to the current date and the user set to the current user.

##### Return

A new drink object with the category set to Bottle

### drinksForUser(user:)

```swift
class func drinksForUser(user: User) -> [Drink]
```

Finds all of the drinks for a given user

##### Parameters

- user: The user whose drinks we are loading

##### Return

An array of drink objects related to the given user

## Instance Methods

### delete()

```swift
func delete()
```

Delete the drink
This method does not actually delete the drink from the database. It just toggles the 'removed' field.

## Constants

### DrinkCategory

DrinkCategory provides an enum for identifying what button was used to create the drink and its quantity in ounces.

| Drink  | Category for a 4oz drink  |
| Glass  | Category for a 8oz drink  |
| Bottle | Category for a 16oz drink |

# User

The user class represents a user of the application

## Properties

- username (_String_): The user's username
- deviceToken (_String_): The last device token from the user's most recent session
- isCurrentUser (_NSNumber_): A boolean for whether or not the user is the user that is currently authenticated
- drinks (_NSSet_): The user's drinks

## Class Methods

### currentUser()

```swift
class func currentUser() -> User
```

Loads the current user.

##### Return

The user that is currently authenticated

## Instance Methods

### drinksToday()

```swift
func drinksToday() -> Int
```

Loads the number of drinks the user has had today.

##### Return

An int whose value corresponds to the number of drinks the user has had today

### lastDrinkDate()

```swift
func lastDrinkDate() -> NSDate?
```

Returns the date of the last drink the user had.

##### Return

The date of the user's last drink. This method returns nil if the user has no drinks.

# NewDrinkViewController

## Properties

- drinkButton (_UIButton!_): The button to create a new drink with the drink category
- glassButton (_UIButton!_): The button to create a new drink with the glass category
- bottleButton (_UIButton!_): The button to create a new drink with the bottle category

- drinkCounterLabel (_UILabel!_): The label that displays how many drinks the user has had today
- drinkTimerLabel (_UILabel!_): The label that creates the drink timer

- drinkTimer (_NSTimer_): The timer that updates the drink timer label ever second

## Instance Methods

### viewDidLoad()

```swift
override func viewDidLoad()
```

This method initializes the view when it is loaded

### viewWillAppear(animated:)

```swift
override func viewWillAppear(animated: Bool)
```

This method prepares the view to be displayed

### newDrinkButtonTapped(sender )

```swift
@IBAction func newDrinkButtonTapped(sender : UIButton)
```

This method is called every time a drink button is tapped

##### Parameters

- sender: The object that initiated the action. Should correspond to one of the button for creating a drink.


### updateDrinkTimer()

```swift
func updateDrinkTimer()
```

This method updates the drink timer.
This method should be called by the drinkTimer at intervals of 1 second.

### updateDrinkCounter()

```swift
func updateDrinkCounter()
```

This method updates the drink counter.

# DrinkHistoryTableViewController

The DrinkHistoryViewController represents a view controller where users view their drink history.

## Properties

- drink (_[Drink]_): The array of drinks being displayed

## Instance Methods

### viewDidLoad()

```swift
override func viewDidLoad()
```

This method initializes the view when it is loaded

### viewWillAppear(animated:)

```swift
override func viewWillAppear(animated: Bool)
```

This method prepares the view to be displayed

### numberOfSectionsInTableView(_) 

```swift
override func numberOfSectionsInTableView(tableView: UITableView) -> Int 
```

This method returns the number of sections in the table

##### Return

The number of sections in the tableview. Since the tableview is unsection this method should return 1.

### tableView(_, numberOfRowsInSection:) 

```swift
override func tableView(tableView: UITableView, numberOfRowsInSection section: Int) -> Int
```

This method looks for the number of rows that should be displayed in the table view

##### Return

The number of rows in the table view. Should correspond to the length of the drinks array.

### tableView(_, cellForRowAtIndexPath indexPath: NSIndexPath) 

```swift
override func tableView(tableView: UITableView, cellForRowAtIndexPath indexPath: NSIndexPath) -> UITableViewCell
```

The cell for the row in the table view at the index specified by the index path

##### Parameters

- indexPath: The index path of the row corresponding to the cell

##### Return

A table view cell for the given row

### reloadDrinks()

```swift
func reloadDrinks()
```

The method to reload the drinks table view.
This method is meant to be called when a change has been made to the drinks and the table view needs to be updated to reflect that change.

# HTTPClient

## Class Methods

### sharedClient()

```swift
class func sharedClient() -> HTTPClient
```

The singleton for the HTTPClient

## Instance Methods

### postNewUser(username:, password:, passwordConfirmation:, success:, failure:)

```swift
func postNewUser(username: String, password: String, passwordConfirmation: String, success: (response: AnyObject?) -> Void, failure: (response: AnyObject?, error: NSError?) -> Void)
```

The method for signing up a new user

##### Parameters

- username: The user's username
- password: The user's password
- password_confirmation: The user's password confirmation
- success: The block to be executed when the user is created
- failure: The block to be executed if the user is not created

### authenticateUser(username:, password:, success:, failure:)

```swift
func authenticateUser(username: String, password: String, success: (response: AnyObject?) -> Void, failure: (response: AnyObject?, error: NSError?) -> Void)
```

##### Parameters

- username: The user's username
- password: The user's password
- password_confirmation: The user's password confirmation
- success: The block to be executed when the user is authenticated
- failure: The block to be executed if the user is not created

### func validateUserStatus(deviceToken:)

```swift
func validateUserStatus(deviceToken: String) -> Bool
```

Validates that a device token is still valid

##### Parameters

- deviceToken: The user's device token

##### Return

A bool corresponding to whether or not the device token is valide

### func getDrinks(deviceToken:, success:, failure:)

```swift
func getDrinks(deviceToken: String, success: (response: AnyObject?) -> Void, failure: (response: AnyObject?, error: NSError?) -> Void)
```

Downloads the user's drinks

##### Parameters

- deviceToken: The user's device token
- success: The block to be executed when the drinks are downloaded
- failure: The block to be executed if the request fails

### func postDrink(drink:, deviceToken:, success:, failure:)

```swift
func postDrink(drink: Drink, deviceToken: String, success: (response: AnyObject?) -> Void, failure: (response: AnyObject?, error: NSError?) -> Void)
```

Posts a new drink to the rails app

##### Parameters

- drink: The Drink to be uploaded
- deviceToken: The user's device token
- success: The block to be executed when the drink is created
- failure: The block to be executed if the request fails


### func syncDrinks(drinks:, deviceToken:, success:, failure:)

```swift
func syncDrinks(drinks: [Drink], deviceToken: String, success: (response: AnyObject?) -> Void, failure: (response: AnyObject?, error: NSError?) -> Void)
```

Trades drink data with the rails app

##### Parameters

- drinks: The drinks on the local device
- deviceToken: The user's device token
- success: The block to be executed in response to the sync
- failure: The block to be executed if the request fails
