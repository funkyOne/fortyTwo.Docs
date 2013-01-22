#Application Authentification

Any agent shouldn't be able to make API calls without proper Authentication Keys.
Agent should have `Fortytwo-AppKey` and `Fortytwo-AppSecret` header present in the call. This Keys represent an app registered with Fortytwo.
  
## App-specific request headers 
```
  Fortytwo-AppKey:sampleApp
  Fortytwo-AppSecret:DSFER45ERF34
```

## User-specific request headers 

After successful login operation the client will get userId and sesion token

```
  Fortytwo-UserId:
  Fortytwo-SessionToken:
```
