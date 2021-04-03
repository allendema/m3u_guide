# m3u_guide

##
Declare the playlist as m3u at the start of the file.

```bash
EXTM3U
```
##
Add EPG to your playlist, usually a "xml" or "gz" file.
Multipe sources should use a comma as a seperator.

```bash
EXTM3U url-tvg="https://epg.example.org/movies/guide.xml,https://epg.example.org/sports/guide.gz"
```

##
Use Logos, example:
```bash
#EXTINF:-1 tvg-logo="https://i.imgur.com/blabla.png", Pizza Channel
```

##
Use groups, example: 
```bash
#EXTINF:-1 group-title="comedy", Comedy Movies HD
```

##
If a channel from another list/source is reliable enough, and it has this format

```bash
http://streaming.smile.tv:1234/live/cafecafe/blueblue/100.ts
```
It should be a part of a playlist, get the full playlist with this method

```bash
http://streaming.smile.tv:1234/get.php?username=USERNAME&password=PASS&type=m3u_plus
```

For the one above it would be:
```bash
http://streaming.smile.tv:1234/get.php?username=cafecafe&password=blueblue&type=m3u_plus
```
With "m3u_plus" we get also the groups, as oposed to just "m3u".

##
If supported, change the output of the streams by adding

```bash
&output=ts
```
 at the end of the playlist link.

##
If a good working stream looks similiar to this

```bash
http://111.222.333.444:8000/play/a06k
```
Get the entire playlist with

```bash
http://111.222.333.444:8000/playlist.m3u8
```
##
Check the URL if it ends with "mono.m3u8" or "chunklist.m3u8"

and replace them with:
```bash
"playlist.m3u8" or "index.m3u8"
```

##
In some cases 
```bash
tvg-id=""
```
is empty, search for the EPG code or remove it for better readability.
