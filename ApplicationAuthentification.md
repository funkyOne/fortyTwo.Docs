#Application Authentification

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

On successful login the client app will receive `userId` and `session token`. Every call to user-specific API method
should be signed with this data.


```http 
POST /users?id=1 HTTP/1.1
Host: fortytwo.cloudapp.net

Fortytwo-UserId: c7a2fa33-cb74-4831-b324-6fcf77d1b682
Fortytwo-SessionToken: 7f989d7216f64921a4660762af60b102
...
```
