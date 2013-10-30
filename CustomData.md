# Custom data

Custom data endpoint allows you to store any data you want.

There are 3 ways to use Custom data service.


## Get Custom Data

### 1 User Attributes 
* `GET /customdata?userId=testUSer` will return user attributes

### 2 Entity Attributes 
* `GET /customdata?entityId=testEntity&entityType=activity` will return entity attributes

### 3 User-scoped entity attributes
* `GET /customdata?userId=testUSer&entityId=testEntity&entityType=activity` will return user-scoped entity attributes(for example, how many times a user tried to accomplish a challenge)


## Create custom data
* `POST /customdata/` - specify query parameters needed for required scope see `Get Custom Data`

###Body
```json
{
"prop1":"value1",
"prop2":"value2"
}
```


## Update custom data
* `PUT /customdata/`
 or
* `POST /customdata/update`

###Body
```json
{
"prop1":"value1",
"prop2":"value2"
}
```
