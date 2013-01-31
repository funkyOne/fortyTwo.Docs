User Management
============================
##Get user

* ```GET /users``` will return the specified user

### Query string parameters

id
: _Required_ **string** - Id of user to find


### Response

```json
{
   "id": "c7a2fa33-cb74-4831-b324-6fcf77d1b682",
   
   "firstName": "John",
   
   "lastName": "Doe",
   
   "userName": "john007",
   
   "dateOfBirth": "2012-03-22T16:56:48-05:00",
   
   "gender": "",
   
   "income": 23456,
   
   "email": "johny@mail.com",
   
   "ageGroup": "adult",
   
   "attributes": "could be anything here",
   
   "sessionToken": "7f989d7216f64921a4660762af60b102",
   
   "sessionTokenExpiration": "2012-03-22T16:56:48-05:00",
   
   "customData": 
      {
         "key": "value",
         "key1": "value1"
      }
}
```

## Create user
```
POST /users
```

### Request body
password
: _Required_ **string** - user password
email
: _Required_ **string** - an email

ageGroup
: _Optional_ **string** - `children` | `youngteen` | `teen` | `youngadult` | `adult` | `elderly` | `nodata`

gender
: _Optional_ **string** -`male` | `female` | `notSpecified`

```json
{
   "password":"nbsd@ret%dfd",
   "email":"example@yahoo.com",
   "ageGroup":"teen",
   "gender":"male"
}
```
###Response
This will return `201 Created` along with the current JSON/XML representation of the user if the creation was a success. See the **Get user** endpoint for more info.

# Defining attributes for a user
tbd
