# We using 2 ways to crawl data from SoundCloud
### Get data using SoundCloud API
> we have a list urls of 50 top tracks, it's a system-playlists which are automatically created by SoundCloud, not belonging to any user (we put it in **url_entry** folder)\
> In my code, I use **top50_url.txt** file to parse because it has less record and will be faster.\
> If you want to have more records, substituting **url_entrypoint** variable in head of code by **top50_url_max.txt**. And this will consume lots of time to processing, approximately 3 hours for entire code ( I remember have 1968 users row, 6632 playlists and more than 10.000 tracks)
###### Prerequisite
Firstly, we send sequence *resolve request* to these top URL to get a lists of *track_id*.
Secondly, we will send request with *tracks* endpoint for each *track_id* to get detail infor of each track and it also contains *user* property, which has *id* of user belonging to that track and we will have a list of *user_id*
###### Get detail users
Then sending request with *users* endpoint and we write all detail information of users to CSV file

###### How to get a tracks and playlists
> Idea: We will loop through each users above and get their playlists and tracks

For playlists, we use */users/playlists* endpoint
And using */users/tracks* endpoint for crawling tracks of users

### Get data using Parse HTML
- We use selenium library so we download chromedriver.exe our version is 95.0.4638.69 
- If you use another version please download at https://sites.google.com/a/chromium.org/chromedriver/downloads
