#Application Authentification

Any agent shouldn't be able to make API calls without proper Authentication Keys.
Agent should have `Fortytwo-AppKey` and `Fortytwo-AppSecret` header present in the call. This Keys represent an app registered with Fortytwo.
  
## App-specific request headers 
```
  Fortytwo-AppKey:test
  Fortytwo-AppSecret:7f989d7216f64921a4660762af60b102
```

## User-specific request headers 

On successful login the client app will receive `userId` and `sesion token`. To be able to use any user-specific API methods developer should sign every request with that data.


```
  Fortytwo-UserId:c7a2fa33-cb74-4831-b324-6fcf77d1b682
  Fortytwo-SessionToken:7f989d7216f64921a4660762af60b102
```
