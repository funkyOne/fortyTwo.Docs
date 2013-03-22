#Files

`POST /files?entityId=2343434&entityType=challenge` will upload and add file to an entity

Expects `multipart/form-data` message. 
Every part of which is a filepart with following headers

```
Content-Disposition: form-data; name="file"; filename="c:\Users\FortyTwoUser\Documents\test.txt"
Content-Type: text/plain
```

`Name` parameter of `Content-Disposition` will be used as an id of the file in scope of the parent entity. 
So it must be unique within the entity scope. 

For example if your entity is supposed to have a screenshot, name your screenshot as `screenshot` when upoading
and use this name when you need to pick out the screenshot from the entity files.

Soon we will add `tags` functionality to files. So it will be easier to store and get multiple files of same "type" within entity (or in global scope).
(ie. if entity can have more than one screenshots - get all entity files with tag `screenshot`)

It's important to specify correct `Content-Type` also, it will be used by file storage to serve the uploaded file.
