INTRODUCTION
- This program lets you schedule and send tweets directly from GitHub.

- It contains a GitHub Action workflow that can be manually triggered or scheduled to run at a particular time of the day. The workflow starts a python script that reads tweets from tweet.json to be sent to Twitter.

- The tweets can include text and an image each.


REQUIREMENTS AND DEPENDENCIES
- Get a twitter developer account.
	This gives you access to the official Twitter API. Instructions on how to go about this are widely available on the web.

- Install python.
	You'll find out how to do that on the official python website - python.org.
	Python 3 is recommended.
	
- Install tweepy.
	This is a wrapper for the twitter API.
	Run "pip install tweepy" on your terminal (without the quotes).


INSTRUCTIONS
- Copy your API key, API secret, access token, and access token secret from your twitter developer portal into a secure location. Make sure you enable read and write access for your access token and secret.

- Fork this repo.

- Open the repo and go to Settings>>>Secrets>>>Actions

- Save the credentials you copied from the twitter developer portal as repository secrets using the nomenclature below:
	- Save the API key as TWITTER_CONSUMER_KEY.
	- Save the API secret as TWITTER_CONSUMER_SECRET_KEY.
	- Save the access token as TWITTER_ACCESS_TOKEN.
	- Save the access token secret as TWITTER_ACCESS_TOKEN_SECRETs.

- Edit tweet.json. Replace "tweet_text" with the text and "image_path" with the file path of the image you want to tweet. You can add as many or as few as possible; just add or remove another line of json following the pattern in the file. 
	- There's a sample of what this looks like in sample_tweet.json.
	- Either text or image can be omitted for any post as exemplified in sample_tweet.json.
	- Line breaks can be inserted in the tweet with the escape sequeence \n.

- Now, your tweeting workflow is ready. You can manually trigger it...
- Or set a run schedule for it to follow.
	- Go to line 6 of .github/workflows/tweet.yml. Delete the # symbol at the start of the line and set your run frequency of choice. This is a great resource for understanding the syntax: https://jasonet.co/posts/scheduled-actions/