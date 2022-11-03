# Apple_Podcast_Downloader 苹果播客下载器
Download all avaliable MP3 files from one podcast channel.
下载某一播客频道的所有的可下载mp3文件

----
## How
In the page source code, you can find useful information in HTML tags, like podcast name, podcast type etc.

You can also find direct links to all the mp3 files of this channel.

Those links are stored in a `<script>` tag that has id equals to `shoebox-ember-data-store`.

If you are viewing the source code in your browser, this line is very close to the end, starting with `<script type="fastboot/shoebox"...... `

Thus, we can use python extract channel name, type(used later as file name), and all mp3 links from the page source.

Retrieve all the mp3 links, save them to local.


---
## How to
1. Go to the Apple podcast page https://podcasts.apple.com/us/genre/podcasts/id26
   If you want to reset the language, change the second regin code.
   For example, change to German. The link would be https://podcasts.apple.com/de/genre/podcasts/id26

2. Find any channel that you like. Copy the url into the `urls` list.
3. Go to line `urllib.request.urlretrieve(link, '/home/kaidi/Downloads/{}.mp3'.format(name))`.
   Change the directory to the place you want to save these mp3 files.
4. If you want to download several files at the same time, change the number in `pool = ThreadPool(5)` will let you parallel given number of tasks. 
5. Run from the beginning.


## If you do not want to use iPython, copy all code into your local .py file and run.
