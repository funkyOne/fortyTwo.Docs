# Activities

## Get all activities 
```
GET /activities/all?orderBy=likes&take=50
```

### Parameters
- **orderBy** _(optional)_ — Sorting field. Default _published_. 
  
  ###### Recognized values:
  - 'published' — sort by publish date, most recent first.
  - 'likes' — sort by likes count, most liked first.
- **take** _(optional)_ — how many activites to return. Default is 20.

## Get activities issued by user
[`Requires user authentication`](https://github.com/funkyOne/fortyTwo.Docs/blob/master/Authentication.md#specifying-user-session-data)
```
GET /activities/my?orderBy=likes&take=50
``` 
will return all user's challenges

### Parameters
- **orderBy** _(optional)_ — Sorting field. Default _published_. 
  
  ###### Recognized values:
  - 'published' — sort by publish date, most recent first.
  - 'likes' — sort by likes count, most liked first.
- **take** _(optional)_ — how many activites to return. Default is 20.

## Create Challenge
[`Requires user authentication`](https://github.com/funkyOne/fortyTwo.Docs/blob/master/Authentication.md#specifying-user-session-data)
```
POST /activities
```

```json
{
  "receivingUserId":"c7a2fa33-cb74-4831-b324-6fcf77d1b682",
  "title":"New Challenge",
  "message":"beat that!",
  "expirationDate":"2012-03-22T16:56:48-05:00"
}
```

in respone you will get `EntityIdInfo` object
```json
{
  "entityId":345678987654,
  "entityType":"activity"
}
```

After creating activity you might want to add files to it using [files API](https://github.com/funkyOne/fortyTwo.Docs/blob/master/Files.md) .
