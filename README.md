---------------------------------------------------
models

Note :- 
Time is in.
RFC 3339 - date time format i.e. 2019-10-12T07:20:50.52Z

The following are not included
create playlist
add track to a playlist
remove track from playlist
delete playlist

commenting
etc...

--------------------------------------------------------

album
    {
        "id": "lDRB2",
        "title": "Imgur Office",
        "description": null,
        "cover_image": "24nLu",
        "views": 13780,
        "likes": 123,
        "artist_id":"" 
     }

tracks
     {
        "id"            : ""
        "song_id"        : ""
        "likes":        123
        "title"         : ""
        "duration"      : "" 
        "release_date"   : ""     
        "artist_id"      : ""
        "album_id"       : ""
        "cover_img_url"   : ""
        "track_url" : ""
        "views" : 34134
        "duration" : 341345135 // milliseconds
        "lyrics_url": ""
    }
    
playlist
{
	"id": ""
	"name": ""
	"created_by":""
	"created_time"
	"type": public || private
	"track_count" : 12 
	"created_at" : date time
}

------------------------------------
End Points
-------------------------------------
Get album list 
"albums"

#tag
recomended
popular
new

#params
page[]
field[]
sort[]
user_id

albums/{tag}?fields[title]=x&page[offset]=0&page[limit]=10&sort[title]=asc&user_id=x

{
  "_metadata": 
  {
      "page": 5,
      "per_page": 20,
      "page_count": 20,
      "total_count": 521,
      "Links": [
        {"self": "/album?page=5&per_page=20"},
        {"first": "/album?page=0&per_page=20"},
        {"previous": "/album?page=4&per_page=20"},
        {"next": "/album?page=6&per_page=20"},
        {"last": "/album?page=26&per_page=20"},
      ]
  },
  "data": [
	// album model list
  ]
}

-----------------------------------------------------

Get track list

"tracks"

#tag
new
popular
recomended

#params
page[]
field[]
sort[]
user_id
tracks/{tag}?fields[title]=x&page[offset]=0&page[limit]=10&sort[title]=asc&user_id=x

{
  "_metadata": 
  {
      "page": 5,
      "per_page": 20,
      "page_count": 20,
      "total_count": 521,
      "Links": [
        {"self": "/tracks?page=5&per_page=20"},
        {"first": "/tracks?page=0&per_page=20"},
        {"previous": "/tracks?page=4&per_page=20"},
        {"next": "/tracks?page=6&per_page=20"},
        {"last": "/tracks?page=26&per_page=20"},
      ]
  },
  "data": [
	// album model list
  ]
}

-------------------------------------------------
Get Album
{
    "data": // album model,
    "success": true,
    "status": 200
}

-------------------------------------------------
Get Track
{
    "data": // track model,
    "success": true,
    "status": 200
}

-------------------------------------------------
Get Playlist
{
    "data": // play list model,
    "success": true,
    "status": 200
}

---------------------------------------
Get Playlists

"playlist"

#tag
user_playlists
new
popular
recomended

#params
page[]
field[]
sort[]

playlist/{tag}?fields[title]=x&page[offset]=0&page[limit]=10&sort[name]=asc

{
  "_metadata": 
  {
      "page": 5,
      "per_page": 20,
      "page_count": 20,
      "total_count": 521,
      "Links": [
        {"self": "/playlist?page=5&per_page=20"},
        {"first": "/playlist?page=0&per_page=20"},
        {"previous": "/playlist?page=4&per_page=20"},
        {"next": "/playlist?page=6&per_page=20"},
        {"last": "/playlist?page=26&per_page=20"},
      ]
  },
  "data": [
	// playlist model list
  ]
}
-----------------------------------------------------------
Get Playlist tracks

"playlist"

#tag
new

#params
page[]
field[]
sort[]

playlist/{id}/tracks?fields[title]=x&page[offset]=0&page[limit]=10&sort[title]=asc

{
  "_metadata": 
  {
      "page": 5,
      "per_page": 20,
      "page_count": 20,
      "total_count": 521,
      "Links": [
        {"self": "/playlist?page=5&per_page=20"},
        {"first": "/playlist?page=0&per_page=20"},
        {"previous": "/playlist?page=4&per_page=20"},
        {"next": "/playlist?page=6&per_page=20"},
        {"last": "/playlist?page=26&per_page=20"},
      ]
  },
  "data": [
	// playlist model list
  ]
}
------------------------------------------------------------
