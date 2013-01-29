#Authenticating an app

Any agent shouldn't be able to make API calls without proper authentication data. The server supports different ways to specify authentification data.

It checks for values in the following order:
  1. Headers
  2. Query string parameters
  3. URL value
  
First found value is used.

##Using http headers

Agent should have `Fortytwo-AppKey` and `Fortytwo-AppSecret` header present in the call. These keys represent an app registered with Fortytwo.
  
```http 
POST /users?id=1 HTTP/1.1
Host: fortytwo.cloudapp.net
  
Fortytwo-AppKey:test
Fortytwo-AppSecret:7f989d7216f64921a4660762af60b102
...
```

##Using URL and query parameters

```
http://fortytwo.cloudapp.net/test/api/users?id=1&appSecret=7f989d7216f64921a4660762af60b102
```

or 

```
http://fortytwo.cloudapp.net/api/users?id=1&appSecret=7f989d7216f64921a4660762af60b102&appKey=test
```

# Specifying user session data
On successful login the client app will receive `userId` and `session token`. Every user-specific API method call
should be signed with this data.

##Using http headers 
```http 
POST /users?id=1 HTTP/1.1
Host: fortytwo.cloudapp.net

Fortytwo-UserId: c7a2fa33-cb74-4831-b324-6fcf77d1b682
Fortytwo-SessionToken: 7f989d7216f64921a4660762af60b102
...
```

##Using URL and query parameters
```
TBD
```

#Authenticating a user 

Every login method on successful login  sends back the following [user](https://github.com/funkyOne/fortyTwo.Docs/blob/master/UserManagement.md#response) object in response.


##By password
```
POST /login
```
### Query string parameters
email
: _Required_ **string** - User email

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
