# SilverStripe Social Feed
Combine social media posts from Facebook, Twitter and Instagram into a single feed.
Each feed is available separately also.

## Installation
```composer require isaacrankin/silverstripe-social-feed```

## Usage

```<% include SocialFeed %>```

Alternatively you can call the `SocialFeed` method directly like so:

```
<ol>
	<% loop SocialFeed %>
		<li>
			<a href="$URL" target="_blank">
				<h4>Type: $Type</h4>
				<p>Created: $Created</p>
				<!-- Use $Data attribute for provider specific data -->
			</a>
		</li>
	<% end_loop %>
</ol>
```

[See a more detailed example](https://github.com/isaacwebfix/silverstripe-social-feed/blob/master/templates/includes/SocialFeed.ss)

The posts are ordered from newest to oldest. 

Within the `SocialFeed` control loop the following values are available:

- `$URL` - a URL for the social media post
- `$Type` - the type of post, either "facebook", "twitter" or "instagram"
- `$Created` - the creation/posted date of the post
- `$Data` - all of the data for a single post in the original structure returned from the API's. Read documentation for the API's to see what's available. 

## Requirements

SilverStripe 3.4 or newer

## Twitter

The Twitter data is a collection of the most recent Tweets posted by the user.
The following API endpoint is used `https://api.twitter.com/1.1/statuses/user_timeline.json?screen_name=twitterapi`

[Twitter API documentation for user timeline](https://dev.twitter.com/rest/reference/get/statuses/user_timeline)

### Credentials
You'll need to create a Twitter app here [https://apps.twitter.com/app/](https://apps.twitter.com/app/)

## Facebook

The Facebook data returned is the most recent posts for a given Facebook Page.
The following API endpoint is used `https://graph.facebook.com/PAGE_ID/feed?access_token=ACCESS_TOKEN`

[Facebook API documentation](https://developers.facebook.com/docs/graph-api/using-graph-api)
 
### Credentials
[TODO - document how to get necessary credentials]

## Instagram
The most recent media published for a user.
The following API endpoint is used `https://api.instagram.com/v1/users/self/media/recent/?access_token=ACCESS_TOKEN`
[Instagram API documentation for resent user media](https://www.instagram.com/developer/endpoints/users/#get_users_media_recent_self)

### Credentials
[TODO - document how to get necessary credentials]
