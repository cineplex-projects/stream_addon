# Stream_addon GUide
This repository guide how a developer/organisation can build a stream addon that can embed and available on cinplex app.

1. Create a folder on your server like helloworld that will kept all files our server will point to this folder.  Folder name can be anything like we used helloworld in this repository. Just open the file manifest.json from helloworld folder and change accordingly.

2. Install cinplex app on your device.  Apk given in repository.

3. Go to addon.  You will find custom plugin textbox.  Here you will need to put your server folder like (http://www.example.org/helloworld/).  Note: right slash is mandatory. our app will look manifest.json in the provided link.  If every thing is ok then a popup will display then your addon name has been successfully installed.

4. Addon installed but for stream app need for stream json for each movie/series. Our app provides catalog from imdb and popular platforms.  This tutorial is limited to imdb only.  You will need imdb id for any movie/series.  This will get from imdb.com screenshot attached for your ready reference.

![alt text](https://github.com/cineplex-projects/stream_addon/screenshots/blob/master/imdb.png?raw=true)

5. create a json with imdb id in folder helloworld/stream/movie/<imd_id>.json or helloworld/stream/series/<imd_id>:<seasonno>:<episodeno>.json

4. We have given both samples in repository helloworld folder for try.  just keep the same file. Search the movie given in screenshot on cineplex app and you will find the stream as per screenshot below.

Notes for Stream Url: 
1) stream url should be valid m3u8, mp4, mkv, magnet uri, pdisk or kofilink, youtube.

2) url will ask to play in the user favorite player that are already installed on his system.

3) If want to get play with cineplex app the a prefix will be required to add in url. (/play?stream_url=<media_url>).  But keep in mind inbuilt player will not compaible for multi audio. So if the stream providing multi audio then will recommend not use of inbuilt player.

4) If want to get play on the mandatory player like playit then need prfix of the player.  See the player docs first for their prefix. For playit ex: playit://playerv2/video?url=<media_url> can be used.  But keep in mind if the player not installed on user system then the cineplex app can be crash and required restart manually.

5) Magent uri will detect the supported app that user have on their device then will give him choice to download and play from the choiced app. We recommend amnis app as this play start immediately before waiting to full content download. alternatively utorrent or other torrent can be used.