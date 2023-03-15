Draft.

## Authorization

To get token, you should call the "token" page:

`/token?username={YOUR USERNAME}&password={YOUR PASSWORD}&grant_type=password`

You'll get a response like this:

```json
{
    "access_token": "THERE IS A TOKEN. A LONG TOKEN ACTUALLY",
    "expires_in": 0,
    "user_id": 1
}
```


### Registration

Register new useer. If login already exist return -1.

#request:
/register?

```json
{
    "login": "login",
    "password": "goodPassword",
    "name": "name",
    "surname": "surname",
    "patronymic": "patronymic"
}
```

#response:
```json
{
    "response":
    {
        "id": 1,
        "banned": false,
        "login": "someLogin",
        "access_token": "THERE IS A TOKEN. A LONG TOKEN ACTUALLY"
        
    }
}
```


### `takeBook(String name, String author)` 

Returns the id book and change status in Book objekt. If book not found (or all in use) return -1. Return -2 if you banned.

#request:
/handler?

```json
{
    "access_token": "THERE IS A TOKEN. A LONG TOKEN ACTUALLY",
    "fname": "getBook",
    "expires_in": "name",
    "user_id": "author"
}
```

#response:
```json
{
    "response":
    {
        "id": 1
    }
}
```

