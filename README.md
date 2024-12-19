# BlockchainTwitter

This smart contract simulates a basic social media platform on the blockchain, where users can tweet, send messages, follow other users, and manage operator permissions. Built on Ethereum or any compatible blockchain, it allows for decentralized interaction and communication.

Features

Tweeting:
Users can post their own tweets.
Operators (authorized users) can post tweets on behalf of other users.

Messaging:
Users can send direct messages to other users.
Operators can send messages on behalf of the user they are authorized by.

Following:
Users can follow other users, building a network of followers.

Operator Management:
Users can grant or revoke operator permissions, allowing others to act on their behalf for tweeting and messaging.

Retrieve Tweets:
Retrieve the latest tweets from all users.
Retrieve the latest tweets from a specific user.


Contract Structure
1. Tweet Struct:
Contains:
ID: Unique identifier for the tweet.
Author: The address of the user who posted the tweet.
Content: The tweet's content.
Timestamp: The time when the tweet was posted.

3. Message Struct:
Contains:
ID: Unique identifier for the message.
Content: The content of the message.
Sender: The address of the message sender.
Receiver: The address of the message receiver.
Timestamp: The time when the message was sent.

Mappings:
tweets: Mapping to store tweets, indexed by tweet ID.
tweetsOf: Mapping to store tweet IDs for each user.
conversations: Mapping to store direct messages between users.
operators: Mapping to manage operator permissions for users.
following: Mapping to store the list of users followed by each user.

Functions
1. _tweet(address _from, string memory _content):
Internal function to handle the logic of posting a tweet.
Ensures that only the user or an authorized operator can post a tweet on their behalf.
2. _sendMessage(address _from, address _to, string memory _content):
Internal function to handle sending messages between users.
Ensures that only the user or an authorized operator can send a message on behalf of a user.

Public Functions:
tweet(string memory _content):

Allows a user to post a tweet by providing tweet content.
tweet(address _from, string memory _content):

Allows an operator to post a tweet on behalf of a user they are authorized by.
sendMessage(string memory _content, address _to):

Allows a user to send a message to another user.
sendMessage(address _from, address _to, string memory _content):

Allows an operator to send a message on behalf of a user they are authorized by.
follow(address _followed):

Allows a user to follow another user.
allow(address _operator):

Allows a user to authorize another user as an operator.
disallow(address _operator):

Allows a user to revoke an operator’s permissions.
getLatestTweets(uint count):

Returns the latest tweets from all users.
getLatestTweetsOf(address user, uint count):

Returns the latest tweets from a specific user.
