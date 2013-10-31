# Custom data

Custom data endpoint allows you to store any data you want.

There are 3 ways to use Custom data service.


## Get Custom Data

### 1 User Attributes 
[`Requires user authentication`](https://github.com/funkyOne/fortyTwo.Docs/blob/master/Authentication.md#specifying-user-session-data)
* `GET /customdata?userId=testUSer` will return user attributes

`userId` is optional, if not specified customdata of currently logged in user will be returned

### 2 Entity Attributes 
[`Requires user authentication`](https://github.com/funkyOne/fortyTwo.Docs/blob/master/Authentication.md#specifying-user-session-data)
* `GET /customdata?entityId=testEntity&entityType=activity` will return an entity attributes

### 3 User-scoped entity attributes
[`Requires user authentication`](https://github.com/funkyOne/fortyTwo.Docs/blob/master/Authentication.md#specifying-user-session-data)
* `GET /customdata?userId=testUSer&entityId=testEntity&entityType=activity` will return user-scoped entity attributes(for example, how many times a user tried to accomplish a challenge)


## Set custom data
* `POST /customdata/` - specify query parameters needed for required scope see `Get Custom Data`

###Body
```json
{
"prop1":"value1",
"prop2":"value2"
}
```

## Update custom data
use #Set custom data# to update. All properties get merged. So you can just specify only properties that must be updated. Nothing will get wiped out.
