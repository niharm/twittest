# Rolling Retweets

## Intro
A retweet is a reposted or forwarded message on Twitter. A retweet retains information about the user who posted the original tweet, as well as the user who retweeted them.

## Objective
Use Twitter's [sample streaming API](https://dev.twitter.com/streaming/reference/get/statuses/sample) to show the top 15 retweeted tweets in a rolling window of time, where the window's start is n minutes ago (where n is defined by the user) and the window's end is the current time.

![Diagram](http://i.imgur.com/PygXeBE.png)

## Details
The output should update every 1000 tweets and include the tweet text and count of retweets in the current window. The Twitter API returns [Tweets](https://dev.twitter.com/docs/platform-objects/tweets) that include the following properties: `created_at`, `id`, `text`, `user`, and `retweeted_status`. If you’re looking for a place to start, think about how you could use the `retweeted_status` field.

As far as JS libraries go, https://github.com/ttezel/twit should work well for this!

### Things to keep in mind
- Original tweets do not have to fall within the time window.
- The sample stream will not capture all of the retweets. You should ignore the `retweet_counts` property and count the retweets that **appear in the sample stream only**.

### Example
```
var stream = T.stream('statuses/sample');
stream.on('tweet', function (tweet) {
  console.log(tweet);
});
```

Please use the following Twitter credentials:

Consumer key (API key):
`qgVAMa6t1yxLz87oYF7hFSf8v`

Consumer secret (API secret):
`k85Rt4vdcTECUN5FIjUHg4bxr7ONfL37XDOCU9Jw7WleewhiuU`

Access token:
`321605011-ZXPL8bnzP9hHPpBDbgB1JqO0ooLxYgFf6UzSjjTr`

Access token secret:
`IPDR5So3VCax0n7AqgHSVKeJy6KnOrmWyltNmolRHATOb`
