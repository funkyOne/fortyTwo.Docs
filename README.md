#42 Web API

## Making a request
All URLs start with `http://fortytwo.cloudapp.net/api` it's our production URL. 

For staging access URLs start with `http://7bdeaa4e4d2f4fcaa4090f9fae5966df.cloudapp.net/api`. Staging server version is usually more recent.


## Authentication
All request to the API must be signed. If you don't supply authentification info, you will get a `400 Bad Request`.
Read the [authentication guide](https://github.com/funkyOne/fortyTwo.Docs/blob/master/ApplicationAuthentification.md) to get started.

## XML or JSON, you decide
The FortyTwo server can serve and handle JSON or XML data. It depends on `ContenType` request header you specify.
* `Content-Type: application/json;charset=utf-8` for JSON
* `Content-Type: application/xml;charset=utf-8` for XML

**Documentation is mostly in JSON, it's preferred and more documented.**

### [Signing requests](https://github.com/funkyOne/fortyTwo.Docs/blob/master/ApplicationAuthentification.md)


## API ready for use

* [User management](https://github.com/funkyOne/fortyTwo.Docs/blob/master/UserManagement.md)

* [Custom data](https://github.com/funkyOne/fortyTwo.Docs/blob/master/CustomData.md)
