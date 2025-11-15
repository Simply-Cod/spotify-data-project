# spotify-data-project
This is a small learning project for anyone who wants to learn parsing JSON data.
Using spotify's data download feature, you can look at your entire listening history and write code to analyze it.

## Challenges
**Easy:** Get your top 5 songs for any given year

**Harder:** Get your all time top 5 songs

### What you will need
- A spotify account
- A way to parse json in your language of choice (Python, C#, Go, etc.)

### How to request data
- go to www.spotify.com and log in to your account
- go to account > privacy settings
- request your expanded streaming history from there
They say this might take up to 30 days, but i recieved mine in 24 hours.

### JSON Files
You will recieve a zip file containing all your data, extract it.
You will most likely have one file pr year, if you stream alot of music then they might be split in to multible files.
the json object looks like this (according to spotify):
```json
{
"ts": "YYY-MM-DD 13:30:30",
"username": "_________",
"platform": "_________",
"ms_played": _________,
"conn_country": "_________",
"ip_addr_decrypted": "___.___.___.___",
"user_agent_decrypted": "_________",
"master_metadata_track_name": "_________,
"master_metadata_album_artist_name:_________",
"master_metadata_album_album_name:_________",
"spotify_track_uri:_________",
"episode_name": _________,
"episode_show_name": _________,
"spotify_episode_uri:_________",
"reason_start": "_________",
"reason_end": "_________",
"shuffle": null/true/false,
"skipped": null/true/false,
"offline": null/true/false,
"offline_timestamp": _________,
"incognito_mode": null/true/false,
}
```
The ones i recieved looked like this

```json
{
    "ts": "YYY-MM-DD 13:30:30",
    "platform": "_________",
    "ms_played": _________,
    "conn_country": "_________",
    "ip_addr": "_________",
    "master_metadata_track_name": "_________",
    "master_metadata_album_artist_name": "_________",
    "master_metadata_album_album_name": "_________",
    "spotify_track_uri": "_________",
    "episode_name": null/true/false,
    "episode_show_name": null/true/false,
    "spotify_episode_uri": null/true/false,
    "audiobook_title": null/true/false,
    "audiobook_uri": null/true/false,
    "audiobook_chapter_uri": null/true/false,
    "audiobook_chapter_title": null/true/false,
    "reason_start": "_________",
    "reason_end": "_________",
    "shuffle": null/true/false,
    "skipped": null/true/false,
    "offline": null/true/false,
    "offline_timestamp": _________,
    "incognito_mode": null/true/false
  } 
```

### Technical field Contains
- **ts:** This field is a timestamp indicating when the track stopped
playing in UTC (Coordinated Universal Time). The order is
year, month and day followed by a timestamp in military time
- **username:**  This field is your Spotify username.
platform This field is the platform used when streaming the track (e.g.
Android OS, Google Chromecast).
- **ms_played:**  This field is the number of milliseconds the stream was
played.
conn_country This field is the country code of the country where the stream
was played (e.g. SE - Sweden).
- **Ip_addr_decrypted:**  This field contains the IP address logged when streaming the
track

- **user_agent_decrypted:**  This field contains the user agent used when streaming the
track (e.g. a browser, like Mozilla Firefox, or Safari)
- **master_metadata_track_name:**  This field is the name of the track.
- **master_metadata_album_artist_name:**  This field is the name of the artist, band or podcast.
- **master_metadata_album_album_name:**  This field is the name of the album of the track.
- **spotify_track_uri:**  A Spotify URI, uniquely identifying the track in the form of
“spotify:track:<base-62 string>”
A Spotify URI is a resource identifier that you can enter, for
example, in the Spotify Desktop client’s search box to locate
an artist, album, or track.
- **episode_name:**  This field contains the name of the episode of the podcast.
- **episode_show_name:**  This field contains the name of the show of the podcast.
- **spotify_episode_uri:**  A Spotify Episode URI, uniquely identifying the podcast
- **episode:**  in the form of “spotify:episode:<base-62 string>”
A Spotify Episode URI is a resource identifier that you can
enter, for example, in the Spotify Desktop client’s search box
to locate an episode of a podcast.
- **reason_start:**  This field is a value telling why the track started (e.g.
“trackdone”)
- reason_end This field is a value telling why the track ended (e.g.
“endplay”).
- **shuffle:**  This field has the value True or False depending on if shuffle
mode was used when playing the track.
- **skipped:**  This field indicates if the user skipped to the next song
- **offline:**  This field indicates whether the track was played in offline
mode (“True”) or not (“False”).
- **offline_timestamp:**  This field is a timestamp of when offline mode was used, if
used.
- **incognito_mode:** This field indicates whether the track was played during a
private session (“True”) or not (“False”).


**Note**
if you have an older account the username field might not be there. but it has not cause any problems for me.
