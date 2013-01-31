#42 Web API

## Making a request

All URLs start with `http://fortytwo.cloudapp.net/test/api` where `test` is your app key.

Or with `http://fortytwo.cloudapp.net/api` if you use other ways to provide appKey the URL (see authentication section for details).

For test / debug access hostname is `37c16b6205f447d4b2e937bae01d30a6.cloudapp.net`. Staging server version is usually more recent, also we have request logging enabled there.


## Authentication
All requests to the API must be signed. If you don't supply authentication info, you will get a `400 Bad Request`.

Read the [authentication guide](https://github.com/funkyOne/fortyTwo.Docs/blob/master/Authentication.md) to get started.

## XML or JSON, you decide
The FortyTwo server can serve and handle JSON or XML data. There are two main ways to tell what format you need.

###"Accept" HTTP header
If a Request message is sent with an `Accept` header, server will use the `Accept` header to decide about the Response media type to write. 
This should make sense to you as here the client is asking for a response in a specific format.

* `Accept: application/json` for JSON
* `Accept: application/xml` for XML

###URL path extention
*still under development*

Soon it will be possible to specify desired response format by url path extention.
You will just need to append `.json` or `.xml` extention to the end of the url path,
like `GET /users.json`
or `GET /users/1.json?someParameter=someValue`
or `GET /users/action.json`

### "Content-type" HTTP header
If a Request message is sent with NO `Accept` header and no URL path extention but with a `Content-Type` header (let’s say when you are using POST to post content), server will use the Content-Type header to decide about the Response media type to write.
`Content-Type: application/xml`

*Documentation is mostly in JSON, it's preferred and more documented.*

## API ready for use

* [User management](https://github.com/funkyOne/fortyTwo.Docs/blob/master/UserManagement.md)

* [Custom data](https://github.com/funkyOne/fortyTwo.Docs/blob/master/CustomData.md)
