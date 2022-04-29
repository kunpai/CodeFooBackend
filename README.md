# Code Foo Backend Project
For Code Foo IGN
Using the .csv file given, I created a Backend server on Flask using SQLite as the database

## Usage

All responses will have the form

```json
{
    "media_type" : row[1],
    "name" : row[2],
    "short_description" : row[5],
    "long_description" : row[4],
    "genres" : row[11],
    "ratings" : row[9],
    "review_url" : row[8],
    "slug" : row[10],
    "published_by" : row[13],
    "franchise": row[14]
}
```
where row is the extraction from the SQLite Database.


Here are the endpoints on the API and what they do:

**Definition**

`GET`, `POST`

**\api\details**

This endpoint takes in a title, converts it into a slug, and checks if any entry in the database fulfils the query.

`POST`:

```json
    {
        "slug" : slug
    }
```
Any string entered is converted into a slug using the string function ```.lower().replace(' ','-')```

`GET` :
- `200 OK`

```json
[
    {
        "media_type" : row[1],
        "name" : row[2],
        "short_description" : row[5],
        "long_description" : row[4],
        "genres" : row[11],
        "ratings" : row[9],
        "review_url" : row[8],
        "slug" : row[10],
    },
]
```

**Definition**

`GET`, `POST`

**\api\recommend**

This endpoint takes in a type of media (Movie, Game, etc.) and a Genre, and returns media that fulfils both categories.

`POST`:

```json
    {
        "media_type" : media_type,
        "genres" : genre
    }
```
Any string entered is converted into the correct format using the string function ```.title()```

`GET` :
- `200 OK`

```json
[
    {
        "media_type" : row[1],
        "name" : row[2],
        "short_description" : row[5],
        "long_description" : row[4],
        "genres" : row[11],
        "ratings" : row[9],
        "review_url" : row[8],
        "slug" : row[10],
    },
]
```

**Definition**

`GET`, `POST`

**\api\publisher**

This endpoint takes in a type of media (Movie, Game, etc.) and a Publisher, and returns media that fulfils both categories.

`POST`:

```json
    {
        "media_type" : media_type,
        "published_by" : publisher
    }
```
Any string entered is converted into the correct format using the string function ```.title()```

`GET` :
- `200 OK`

```json
[
    {
        "media_type" : row[1],
        "name" : row[2],
        "short_description" : row[5],
        "long_description" : row[4],
        "genres" : row[11],
        "ratings" : row[9],
        "review_url" : row[8],
        "slug" : row[10],
        "published_by" : row[13]
    },
]
```

**Definition**

`GET`, `POST`

**\api\franchise**

This endpoint takes in a Franchise, and returns media that fulfils that category.

`POST`:

```json
    {
        "franchise" : franchise
    }
```
Any string entered is converted into the correct format using the string function ```.title()```

`GET` :
- `200 OK`

```json
[
    {
        "media_type" : row[1],
        "name" : row[2],
        "short_description" : row[5],
        "long_description" : row[4],
        "genres" : row[11],
        "ratings" : row[9],
        "review_url" : row[8],
        "slug" : row[10],
        "franchise" : row[14]
    },
]
```

**Definition**

`GET`, `POST`

**\api\mediafranchise**

This endpoint takes in a type of media (Movie, Game, etc.) and a Publisher, and returns media that fulfils both categories.

`POST`:

```json
    {
        "media_type" : media_type,
        "franchise" : franchise
    }
```
Any string entered is converted into the correct format using the string function ```.title()```

`GET` :
- `200 OK`

```json
[
    {
        "media_type" : row[1],
        "name" : row[2],
        "short_description" : row[5],
        "long_description" : row[4],
        "genres" : row[11],
        "ratings" : row[9],
        "review_url" : row[8],
        "slug" : row[10],
        "franchise" : row[14]
    },
]
```




