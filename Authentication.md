#Authenticating an app

Any agent shouldn't be able to make API calls without proper Authentication Keys.
Agent should have `Fortytwo-AppKey` and `Fortytwo-AppSecret` header present in the call. These keys represent an app registered with Fortytwo.
  
## App-specific request headers 
```http 
POST /users?id=1 HTTP/1.1
Host: fortytwo.cloudapp.net
  
Fortytwo-AppKey:test
Fortytwo-AppSecret:7f989d7216f64921a4660762af60b102
...
```

## User-specific request headers 

On successful login the client app will receive `userId` and `session token`. Every user-specific API method call
should be signed with this data.


```http 
POST /users?id=1 HTTP/1.1
Host: fortytwo.cloudapp.net

Fortytwo-UserId: c7a2fa33-cb74-4831-b324-6fcf77d1b682
Fortytwo-SessionToken: 7f989d7216f64921a4660762af60b102
...
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
