# Challenges



## Get custom data
* `GET /customdata/` 

## Create Challenge

* `POST /newchallenges`

```json
{
  "challengerId":"",
  "title":"New Challenge",
  "expirationDate":"2012-03-22T16:56:48-05:00"
}
```

user must be logged in to create a challenge

in respone you will get `EntityIdInfo` object
```json
{
  "entityId":345678987654,
  "entityType":"challenge"
}
```

After creating chanllenge you might want to add files to it using [files api](https://github.com/funkyOne/fortyTwo.Docs/blob/master/Files.md) .
