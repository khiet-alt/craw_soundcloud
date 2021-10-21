# We using 2 ways to crawl data from SoundCloud
-----------
#### Get data using SoundCloud API
=========
> we have a list urls of 50 top tracks, it's a system-playlists which are automatically created by SoundCloud, not belonging to any user.
Firstly, we send sequence *resolve request* to these top URL to get a lists of *track_id*.
Secondly, we will send request with *tracks* endpoint for each *track_id* to get detail infor of each track and it also contains *user* property, which has *id* of user belonging to that track and we will have a list of *user_id*
**Get infor user:** Then sending request with *users* endpoint and we write all detail information of users to CSV file

###### How to get a tracks and playlists
> Idea: We will loop through each users above and get their playlists and tracks
For playlists, we use */users/playlists* endpoint
And using */users/tracks* endpoint for crawling tracks of users

#### Get data using Parse HTML
=========
