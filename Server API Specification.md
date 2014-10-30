# Server API Specification

## Users

### Create A New User

##### Route

```
POST /api/v1/users.json
```

##### Example Parameters

```JSON
{
  "user":{
    "username":"example_user",
    "password":"1234abcd",
    "password_confirmation":"1234abcd"
  }
}
```

##### Example Response

```JSON
{
  "username":"example_user",
  "device_token":"aa22f6d3-4d0b-4c8c-a089-1cfb4863aefe"
}
```

### Authenticate An Existing User

##### Route

```
POST /api/v1/users/authenticate.json
```

##### Example Parameters

```JSON
{
  "username":"example_user",
  "password":"1234abcd",
}
```

##### Example Response

```JSON
{
  "username":"example_user",
  "device_token":"23787b11-d2ae-4ada-8d00-b4e0987e8343"
}
```

## Drinks

### Create A New Drink

##### Route

```
POST /api/v1/drinks.json
```

##### Example Parameters

```JSON
{
  "device_token":"aa22f6d3-4d0b-4c8c-a089-1cfb4863aefe",
  "drink":{
    "category":"glass",
    "uuid":"4b0af139-550b-4a36-a85a-017dac597d0f",
    "drink_date":"2010-05-30T06:14:00Z"
  }
}
```

##### Example Response

```JSON
{
  "category":"glass",
  "uuid":"4b0af139-550b-4a36-a85a-017dac597d0f",
  "drink_date":"2010-05-30T06:14:00.000Z"
}
```

### Load All Drinks

##### Route

```
GET /api/v1/drinks.json?device_token={{device_token}}
```

##### Example Response

```JSON
[
  {
    "category":"glass",
    "uuid":"4b0af139-550b-4a36-a85a-017dac597d0f",
    "drink_date":"2010-05-30T06:14:00.000Z"
  },
  {
    "category":"drink",
    "uuid":"1955958c-d0a2-4fe4-ba87-772ebd403013",
    "drink_date":"2010-05-30T06:14:00.000Z"
  },
  {
    "category":"bottle",
    "uuid":"636aaaf1-3c35-497a-941c-27a592134055",
    "drink_date":"2010-05-30T06:14:00.000Z"
  }
]
```

### Synchronize Drinks

##### Route

```
POST /api/v1/drinks/sync.json
```

##### Example Parameters

```JSON
{
  "device_token":"aa22f6d3-4d0b-4c8c-a089-1cfb4863aefe",
  "drinks":[
    {"drink":{
      "category":"glass",
      "uuid":"4b0af139-550b-4a36-a85a-017dac597d0f",
      "drink_date":"2010-05-30T06:14:00Z"
    }},
    {"drink":{
      "category":"drink",
      "uuid":"1955958c-d0a2-4fe4-ba87-772ebd403013",
      "drink_date":"2010-05-30T06:14:00Z"
    }}
  ]
}
```

##### Example Response

```JSON
[
  {
    "category":"glass",
    "uuid":"4b0af139-550b-4a36-a85a-017dac597d0f",
    "drink_date":"2010-05-30T06:14:00.000Z"
  },
  {
    "category":"drink",
    "uuid":"1955958c-d0a2-4fe4-ba87-772ebd403013",
    "drink_date":"2010-05-30T06:14:00.000Z"
  },
  {
    "category":"bottle",
    "uuid":"636aaaf1-3c35-497a-941c-27a592134055",
    "drink_date":"2010-05-30T06:14:00.000Z"
  }
]
```