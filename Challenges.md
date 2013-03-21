# Challenges

Custom data endpoint allows you to store any data you want.

## Get custom data
* `GET /customdata/` will return authentificated user's custom data
 depending on parameters specified


## Create Challenge

* `POST /newchallenges`
```
{
  "challengerId":"",
  "title":"New Challenge",
  "expiration":""
}
```
user must be logged in to create a challenge

