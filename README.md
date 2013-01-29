#42 Web API

## Making a request
All URLs start with `http://fortytwo.cloudapp.net/api` it's our production URL. 

For staging access URLs start with `http://37c16b6205f447d4b2e937bae01d30a6.cloudapp.net/api`. Staging server version is usually more recent.


## Authentication
All request to the API must be signed. If you don't supply authentication info, you will get a `400 Bad Request`.
Read the [authentication guide](https://github.com/funkyOne/fortyTwo.Docs/blob/master/Authentication.md) to get started.

## XML or JSON, you decide
The FortyTwo server can serve and handle JSON or XML data. It depends on `ContenType` request header you specify.
* `Content-Type: application/json;charset=utf-8` for JSON
* `Content-Type: application/xml;charset=utf-8` for XML

**Documentation is mostly in JSON, it's preferred and more documented.**

### [Authentication](https://github.com/funkyOne/fortyTwo.Docs/blob/master/Authentication.md)


## API ready for use

* [User management](https://github.com/funkyOne/fortyTwo.Docs/blob/master/UserManagement.md)

* [Custom data](https://github.com/funkyOne/fortyTwo.Docs/blob/master/CustomData.md)
