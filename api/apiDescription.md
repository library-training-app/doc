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


## Registration

Register new user. If login already exist return in all fields -1.

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


## takeBook(String name, String author)

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

## returnBook(book.id)

Returns the boolean true.
#request:
/handler?

```json
{
    "access_token": "THERE IS A TOKEN. A LONG TOKEN ACTUALLY",
    "fname": "returnBook",
    "booId": "book.id"
}
```

#response:
```json
{
    "response":
    {
        "succes": true
    }
}
```

## getListOfBooks(user.id)

returns a list of books from the user
#request:
/handler?

```json
{
    "access_token": "THERE IS A TOKEN. A LONG TOKEN ACTUALLY",
    "fname": "getListOfBooks",
    "id": "user.id"
}
```

#response:
```json
{
    "response":
    {
        "book.id": {
            "name": book.name,
            "author": book.author,
            "yearWrite": same,
            "pagesTotal": same,
            "quality": same,
            "publisher": same,
            "annotation": same,
            "content": same
        },
            ...
        "book.id": {
            "name": book.name,
            "author": book.author,
            "yearWrite": same,
            "pagesTotal": same,
            "quality": same,
            "publisher": same,
            "annotation": same,
            "content": same
        }
    }
}
```

