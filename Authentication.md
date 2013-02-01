#Authenticating an app

Any agent shouldn't be able to make API calls without proper authentication data. The server supports different ways to specify authentification data.

It checks for values in the following order:
  1. HTTP headers
  2. Query string parameters
  3. URL path fragment
  
First found value is used.

##Using HTTP headers

Agent should have `Fortytwo-AppKey` and `Fortytwo-AppSecret` header present in the call. These keys represent an app registered with Fortytwo.
  
```http 
POST /users?id=1 HTTP/1.1
Host: fortytwo.cloudapp.net
  
Fortytwo-AppKey:test
Fortytwo-AppSecret:7f989d7216f64921a4660762af60b102
...
```

##Using URL path and query parameters
If you go this way, you will always need to specify `appSecret` as query string parameter. With `appKey` you have two options. First is to specify it as a part of URL path :

```
http://fortytwo.cloudapp.net/test/api/users?id=1&appSecret=7f989d7216f64921a4660762af60b102
```

where `test` is your app key.

The second way is to provide both parameters through query string:

```
http://fortytwo.cloudapp.net/api/users?id=1&appSecret=7f989d7216f64921a4660762af60b102&appKey=test
```

# Specifying user session data
On successful login the client app will receive `userId` and `session token`. Every user-specific API method call
should be signed with this data.

##Using HTTP headers 
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

On succesfull sign in operation, server sends back `LoginResult` object:
```json
  {
    "userId":"d067eda6-6414-430f-a0eb-c8455d648b59",
    "sessionToken":"1af5f70841f4a1eb139cf8ec66cce2c7",
    "sessionExpiresAt":"2012-03-22T16:56:48-05:00"    
  }	
```

##By password
```
POST /login?password=123456&email=testuser@mail.com
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
