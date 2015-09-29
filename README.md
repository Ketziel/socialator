#What does this plugin actually do?

Socialator lets you create a combined social feed, pulling from various social media platforms, and outputting it as HTML.

This allows for complete control and styling of each post, and eliminates the need for horrible old iframes to embed social feeds (Hurray!).


#Using this thing

Calls to this snippet can accept a large number of perameters. These must be set for each platform. If any vital details are **not** specified for a particular social platform, the posts from that platform will **not** be included in the output of Socialator. 

Getting all the required variables for each platform can be quite the chore. Below are rough guides to getting started with each platform. However, first is a list of general parameters for plugin usage which is not tied to a specific platform.


#Options to help you do the do

Outwith the settings for each specific platform, are these generic plugin settings. Use thee to control how the plugin manages the data once it has been received from each social media site.

| Name                      | Type              | Default  Value  | Description                                                                                                                              |
| -----------------------|-----------------|-----------------|-----------------------------------------------------------------------------------------------------------------|
| outerClass                |string              | 'socialPosts'     | A class name which will be applied to the container created to hold the list of posts.                                  |
| postCount               |integer            | '25'     | Specifies the number of posts to display. This will be listed by the newest first across all included social platforms.    |
| timeZone               |string            | 'Europe/London'     | Sets the timezone for all DateTime objects to follow.    |
| toPlaceholder               |string            | ''     | overrides the output of the plugin to parse to a placeholder vairable instead.    |


#Twitter

Twitter integration is fairly straight forward, and should cause only a minor headache at worst, so long as everything has been set up correctly on twitter.

The first step to creating a suitable twitter account to use, requires you to attach a phone number to your twitter account. Yes, this is horrible, and yes It would be better if this were not needed, but unfortunately it is. And twitter is not the only one which does. It's worth noting, that the account used to generate the keys **does not** need to be the same as the feed you are wanting to pull. This can be done via your account settings, or you can just continue on and twitter will force you to set a number during the rest of the process.

To generate the keys for this plugin to use, you need to create a new app. Visit [apps.twitter.com](https://apps.twitter.com) and select `Create New App`. Pick a name add a description and most importantly **include the domain you are using the plugin on** in the `Website` field. Callback URL is not required, and can be left blank.

Once you have created this (and got past the unique name check), you'll be able to view and edit your app settings. Click on `Keys and Access Tokens` to get the correct parameters needed by Socialator.

You will need to take a copy of the `Consumer Key`, `Consumer Secret`, `Access Token` & `Access Token Secret`. The latter two of these may require you to generate them first, by clicking on `Create my access token`.

And that's it, that's all the info you require to set up twitter. It's then just a case of plugging these values into the snippet call using the appropriate parameter fields.

| Name                      | Type              | Default  Value  | Description                                                                                                                              |
| -----------------------|-----------------|-----------------|-----------------------------------------------------------------------------------------------------------------|
| twitterAccessToken*   |string              | ''     | Access token for twitter account - required to retreive posts.                                  |
| twitterAccessTokenSecret*   |string              | ''     | Access token Secret for twitter account - required to retreive posts.                                  |
| twitterConsumerKey*   |string              | ''     | Consumer Key for twitter account - required to retreive posts.                                  |
| twitterConsumerSecret*   |string              | ''     | Consumer Secret for twitter account - required to retreive posts.                                  |
| twitterHandle   |string              | ''     | Specifies a twttier account to pull the feed from. If left as default, posts will be pulled from the account used to generate the tokens.|
| twitterRetweets   |boolean              | '0'     | Sets wither the feed should include retweets or not.|
*Required for Twitter posts to be included


#Facebook

So, you've decided to include Facebook in your custom social feed. Prepare your butt, because this can get fiddly.

The first thing that must be done, is registering a Dev account with facebook. The account must be an admin of the page you wish to pull the feed from. This unfortunately requires you to attach a phone number to the account too. Do this by heading to [developers.facebook.com](https://developers.facebook.com) - sign in, and click on the `Register as a Developer` button. It is vital that this account is set up correctly, has the proper permissions and is part of the correct group to control the page.

Next, we want to Create a new App. Select `Choose Apps` in the navigation, and click on `Add a New App`. Follow Quick Start through, most importantly **fill in the Site Domain** to the website field. Choose a category, and then you can skip the rest 

Once this has been created, you will need to retrieve the `App Id` & the `App Secret` from your created app.

Now, we need to retrieve the `Page Id` for the feed which we are trying to pull from. There are number of services online which make this simple, just search google for a site which will retrieve the `Page Id` from a given facebook URL. There are plenty out there, so you should have no trouble finding one that works.

With these values, you can now send these into Socialator, and retrieve the posts from the facebook feed.

| Name                      | Type              | Default  Value  | Description                                                                                                                              |
| -----------------------|-----------------|-----------------|-----------------------------------------------------------------------------------------------------------------|
| facebookPageId*   |string              | ''     | Unique id of the facebook page - required to retreive posts.                                  |
| facebookAppId*   |string              | ''     | Unique id of your generated facebook app - required to retreive posts.                                  |
| facebookAppSecret*   |string              | ''     | Unique Secret id of your generated facebook app - required to retreive posts.                                  |
*Required for Facebook posts to be included

If you've made it this far, and and everything is working then congratulations! You've made it through the land of dragons safely, and can now successfully include custom styled facebook posts on your ModX site.
Otherwise, if you still are unable to retrieve facebook posts - step back, take a breath, read over the steps again, review the account privileges and keep in mind this pearl of wisdom from Zuckerberg himself.
 
 > Move fast and break things. Unless you are breaking stuff, you are not moving fast enough.
 
No one could sum up working with facebook feeds any better.


#What License I done gone used

Socialator is under the [WTFPL](//www.wtfpl.net/) License.