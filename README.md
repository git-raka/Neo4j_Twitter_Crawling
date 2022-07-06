# twitter_crawl_neo4j


get following from cypher neo4j
###FOLLOWING###
WITH apoc.static.getAll("twitter") AS twitter
CALL apoc.load.jsonParams(
  twitter.user2 + "107886941/following?user.fields=created_at&expansions=pinned_tweet_id&tweet.fields=created_at",
  {Authorization:"Bearer "+twitter.bearer},
  null // payload
)
YIELD value
RETURN value.data
========================================================================================================================
###RETWEET###
WITH apoc.static.getAll("twitter") AS twitter
CALL apoc.load.jsonParams(
  twitter.retweet + "1543998368040435712/retweeted_by?user.fields=created_at&expansions=pinned_tweet_id&tweet.fields=created_at",
  {Authorization:"Bearer "+twitter.bearer},
  null // payload
)
YIELD value
RETURN value

========================================================================================================================
###FOLLOWING###
WITH apoc.static.getAll("twitter") AS twitter
CALL apoc.load.jsonParams(
  twitter.user2 + "107886941/following?user.fields=created_at&expansions=pinned_tweet_id&tweet.fields=created_at",
  {Authorization:"Bearer "+twitter.bearer},
  null // payload
)
YIELD value
RETURN value.data
