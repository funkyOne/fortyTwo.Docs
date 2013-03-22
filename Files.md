#Files

`POST /files?entityId=2343434&entityType=challenge` will upload and add file to an entity

Expects `multipart/form-data` message. 
Every part of which is be a filepart with following headers

```
Content-Disposition: form-data; name="file"; filename="c:\Users\FortyTwoUser\Documents\test.txt"
Content-Type: text/plain
```

`Name` parameter of `Content-Disposition` will be used as an id of the file in scope of the parent entity.
