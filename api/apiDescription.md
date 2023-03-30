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

## EditPerson 

Edit some field on user object. Can do user (for self) or admin (for all)

#request:
/handler?

```json
{
    "access_token": "THERE IS A TOKEN. A LONG TOKEN ACTUALLY",
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
        "succes": true
    }
}
```

## DeletePerson 

Remove from dataBase

#request:
/handler?

```json
{
    "access_token": "THERE IS A TOKEN. A LONG TOKEN ACTUALLY",
    "login": "login",
    "id": "id"
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

## takeBook(String name, String author)

Returns the id book and change status in Book objekt. If book not found (or all in use) return -1. 

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

Returns the boolean true. Can do only admin.

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

returns a list of books from the user.

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
            "name": "book.name",
            "author": "book.author",
            "yearWrite": "book.year",
            "quality": "book.quality",
            "media": "book.media"
        },
        "book.id": {
            "name": "book.name",
            "author": "book.author",
            "yearWrite": "book.year",
            "quality": "book.quality",
            "media": "book.media"
        }
    }
}
```

