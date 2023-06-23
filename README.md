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



