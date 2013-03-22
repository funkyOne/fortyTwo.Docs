# Challenges
*Base url `/newchallenges` is temporary. Soon will be merged and moved to `/challenges`*


## Get challenges
* `GET /newchallenges?orderBy=likes&take=20` will return public challenges

*orderBy* - likes | published(default)

both parameters are optional

## Get user challenges
* `GET /newchallenges/my?orderBy=likes&take=20` will return all user's challenges

*request must be signed with sessionKey*

parameters are same as in get public challenges method

## Create Challenge

* `POST /newchallenges`

```json
{
  "receivingUserId":"c7a2fa33-cb74-4831-b324-6fcf77d1b682",
  "title":"New Challenge",
  "message":"beat that!",
  "expirationDate":"2012-03-22T16:56:48-05:00"
}
```

*user must be logged in to create a challenge*

in respone you will get `EntityIdInfo` object
```json
{
  "entityId":345678987654,
  "entityType":"challenge"
}
```

After creating chanllenge you might want to add files to it using [files api](https://github.com/funkyOne/fortyTwo.Docs/blob/master/Files.md) .
