User Management
============================
##Get user

* ```GET /users``` will return the specified user

### Query string parameters

id
: _Required_ **string** - Id of user to find

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
email
: _Optional_ **string** - an email

ageGroup
: _Optional_ **string** - `children` | `youngteen` | `teen` | `youngadult` | `adult` | `elderly` | `nodata`

gender
: _Optional_ **string** -`male` | `female` | `notSpecified`

```json
{
   "email":"example@yahoo.com",
   "ageGroup":"teen",
   "gender":"male"
}
```
###Response
This will return `201 Created` along with the current JSON/XML representation of the user if the creation was a success. See the **Get user** endpoint for more info.

#Authenticating a User 

Every login method on successful login  sends back the following User object in response:


##Password login
```
POST /login
```
### Query string parameters
userId
: _Required_ **string** - Logged user id

password
: _Required_ **string** - User password

##Facebook login
```
POST /login/facebook
```

### Query string parameters
userId
: _Optional_ **string** - Id of user to find, if it's empty a new user is created and his userId is returned in body

accessToken
: _Required_ **string** - Access token got from Facebook

##Twitter login
```
POST /login/twitter
```
### Query string parameters
userId
: _Optional_ **string** - Id of user to find, if it's empty a new user is created and his userId is returned in body

accessToken
: _Required_ **string** - OAuth access token got from Twitter

accessTokenSecret
: _Required_ **string** - OAuth access token secret got from Twitter
