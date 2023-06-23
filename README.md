# Youtube
This repository contains python codes using YouTube data api to do bunch of things that fit my workflow. Wish it will be somehow helpful for you too
Under the file "YouTube.py", I use python packages to handle various YouTube data through YouTube Data Api. (Just wrap the api function to something I frequently used) Feel free to use them and modity/add functionalities you need. On my YouTube channel, there are tutorial on each functions and I hope they are helpful. Cheers~

https://www.youtube.com/channel/UC8MJ9DyPqRzXNYuE0lZo8rA

## Some important points
Check your brand accounts: https://myaccount.google.com/brandaccounts
Time format used for YouTube video scheduling: https://www.w3.org/TR/NOTE-datetime
1. Create a project and an Oauth client. https://console.developers.google.com/
	- Create a new project and enable the YouTube Data API v3.
	- Create API credentials (OAuth 2.0 Client ID).
	- Download the JSON file containing your credentials.
	- Install the required libraries: (I use miniconda and it works fine out of the box)
2. Install the Google Client Library using pip: `pip install google-api-python-client google-auth google-auth-oauthlib google-auth-httplib2`.
The version number combination the work for me is:

google-api-core	2.11.1
google-api-python-client	2.89.0
google-auth	2.20.0
google-auth-httplib2	0.1.0
google-auth-oauthlib	1.0.0
googleapis-common-protos	1.59.1

3. The category list for US (you can get the category list for your country by running the `get_category_ids` function in the code). The category list for US (I think most of countries, the list is the same) To find your country code, go to this link https://en.wikipedia.org/wiki/List_of_ISO_3166_country_codes
{'Film & Animation': '1',
 'Autos & Vehicles': '2',
 'Music': '10',
 'Pets & Animals': '15',
 'Sports': '17',
 'Short Movies': '18',
 'Travel & Events': '19',
 'Gaming': '20',
 'Videoblogging': '21',
 'People & Blogs': '22',
 'Comedy': '34',
 'Entertainment': '24',
 'News & Politics': '25',
 'Howto & Style': '26',
 'Education': '27',
 'Science & Technology': '28',
 'Nonprofits & Activism': '29',
 'Movies': '30',
 'Anime/Animation': '31',
 'Action/Adventure': '32',
 'Classics': '33',
 'Documentary': '35',
 'Drama': '36',
 'Family': '37',
 'Foreign': '38',
 'Horror': '39',
 'Sci-Fi/Fantasy': '40',
 'Thriller': '41',
 'Shorts': '42',
 'Shows': '43',
 'Trailers': '44'}

## Currently wrapped function
- authenticate(scopes = SCOPES,storelocation=os.path.join(PROJECT_LOCATION, BRAND_ACCOUNT_NAME + 'token.json'))
    ''' This function checks if the access token is valid. If not (or nonexistent), it goes through the Oauth2 to obtain 
    an access token and store it under PROJECT_LOCATION/token.json'''
- search_name_find_id(name,channelid=BRAND_ACCOUNT_CHANNEL_ID, typetosearch = 'video',numberofresult=5)
    '''
    Given a query and type to search. Return a list of result with number of results specified
    parameters:
    name: search query
    channelid: the search scope. If provided, it only search results in that specified channel
    typeofsearch : video,channel,playlist
    numbertosearch: Limiting the number of results
    '''
- get_recently_uploaded_videos(channel_id=BRAND_ACCOUNT_CHANNEL_ID, max_results=10)
    '''Get the most recent videos uploaded by the channel  '''  
- get_playlist_videos(channel_id,playlistname, max_results=50)
'''THis function gets all uploaded videos in a playlist with max_result amount'''
- upload_video(status='public',scheduled=None,foldername='Youtubeupload')
    '''This function uploads videos to a specified brand account with title and description'''
- get_playlists(channel_id=BRAND_ACCOUNT_CHANNEL_ID)
- create_playlist(playlist_title,description,status='public',channel_id=BRAND_ACCOUNT_CHANNEL_ID)
- upload_thumbnail(thumbnail_path=r'D:\Online biz\Vocalized learning\python_project.png', video_id='')
'''Upload the thumbnail from the local disk to a playlist or a video
video_id can be playlist_id'''
- add_to_playlist(video_id,playlist_id,mainvideo=False)
'''Given a video_id of uploaded video and a playlist_id, add the video to the playlist with the option of whether
    setting the video to be the main video'''
- get_category_ids(regionCode='US')
'''Get the category id of a region given by ISO 3166 regionCode'''


