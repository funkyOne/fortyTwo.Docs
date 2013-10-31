# Custom data

Custom data endpoint allows you to store any data you want. There are 3 scopes of custom data.


## Get Custom Data

### User Attributes 
[`Requires user authentication`](https://github.com/funkyOne/fortyTwo.Docs/blob/master/Authentication.md#specifying-user-session-data)
* `GET /customdata?userId=755f8447-ab92-4b98-ab30-59cffd1ae989` will return user attributes

`userId` is optional, if not specified customdata of currently logged in user will be returned

### Entity Attributes 
[`Requires user authentication`](https://github.com/funkyOne/fortyTwo.Docs/blob/master/Authentication.md#specifying-user-session-data)
* `GET /customdata?entityId=testEntity&entityType=activity` will return an entity attributes

### User-scoped entity attributes
[`Requires user authentication`](https://github.com/funkyOne/fortyTwo.Docs/blob/master/Authentication.md#specifying-user-session-data)
* `GET /customdata?userId=755f8447-ab92-4b98-ab30-59cffd1ae989&entityId=testEntity&entityType=activity` will return user-scoped entity attributes(for example, how many times a user tried to accomplish a challenge)


## Set custom data
* `POST /customdata/` - single method to create and update custom data, works as "create or merge"

Specify query parameters for scope you need according to `Get Custom Data` section

###Body
```json
{
"prop1":"value1",
"prop2":"value2"
}
```

## Update custom data
Use `Set custom data` to update. All properties get merged. So you can specify only properties that you update/add. Nothing will get wiped out.
