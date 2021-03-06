#Authenticating an app

Any agent shouldn't be able to make API calls without proper authentication data. The server supports different ways to specify authentification data.

It checks for values in the following order:
  1. Query string parameters
  2. HTTP headers
  3. URL path fragment
  
First found value is used.

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

##Using HTTP headers

Agent should have `Fortytwo-AppKey` and `Fortytwo-AppSecret` header present in the call. These keys represent an app registered with Fortytwo.
  
```http 
POST /users?id=1 HTTP/1.1
Host: fortytwo.cloudapp.net
  
Fortytwo-AppKey:test
Fortytwo-AppSecret:7f989d7216f64921a4660762af60b102
...
```

# Specifying user session data
On a successful login your client app will receive `session token`. Every user-specific API method call
should be signed with it.

##Using HTTP headers 
```http 
POST /users?id=1 HTTP/1.1
Host: fortytwo.cloudapp.net

Fortytwo-SessionToken: 7f989d7216f64921a4660762af60b102
...
```

##Using URL and query parameters
```
http://fortytwo.cloudapp.net/api/users?sessionToken=1af5f70841f4a1eb139cf8ec66cce2c7
```

#Authenticating a user 

On a successfull sign in operation, the server sends back `LoginResult` object:
```json
  {
    "userId":"d067eda6-6414-430f-a0eb-c8455d648b59",
    "sessionToken":"1af5f70841f4a1eb139cf8ec66cce2c7",
    "sessionExpiresAt":"2012-03-22T16:56:48-05:00"    
  }	
```

##By password
```
POST /login
```

```json
  {
    "password":"1121213",
    "email":"user@email.com"
  }  
```

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

##Device Id Login
```
POST /login/device
```
### Query string parameters
deviceId
: _Required_ **string** - A sting that uniquely identifies user's device
