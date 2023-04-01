## A step by step guide

- #### Step 1: Requirements clarifications
  - Will users of our service be able to post tweets and follow other people?
  - Should we also design to create and display the user’s timeline?
  - Will tweets contain photos and videos?
  - Are we focusing on the backend only or are we developing the front-end too?
  - Will users be able to search tweets?
  - Do we need to display hot trending topics?
  - Will there be any push notification for new (or important) tweets?
- #### Step 2: System interface definition
- #### Step 3: Back-of-the-envelope estimation
  - What scale is expected from the system
  - How much storage will we need? We will have different numbers if users can have photos and videos in their tweets.
  - What network bandwidth usage are we expecting? This will be crucial in deciding how we will manage traffic and balance load between servers.
- #### Step 4: Defining data model
  - User: UserID, Name, Email, DoB, CreationData, LastLogin, etc.
  - Tweet: TweetID, Content, TweetLocation, NumberOfLikes, TimeStamp, etc.
  - UserFollowo: UserdID1, UserID2
  - FavoriteTweets: UserID, TweetID, TimeStamp
- #### Step 5: High-level design
- #### Step 6: Detailed design
  - Since we will be storing a massive amount of data, how should we partition our data to distribute it to multiple databases? Should we try to store all the data of a user on the same database? What issue could it cause?

  - How will we handle hot users who tweet a lot or follow lots of people?
  - Since users’ timeline will contain the most recent (and relevant) tweets, should we try to store our data in such a way that is optimized for scanning the latest tweets?
  - How much and at which layer should we introduce cache to speed things up?
  - What components need better load balancing?
- #### Step 7: Identifying and resolving bottlenecks
  - Is there any single point of failure in our system? What are we doing to mitigate it?
  - Do we have enough replicas of the data so that if we lose a few servers we can still serve our users?
  - Similarly, do we have enough copies of different services running such that a few failures will not cause total system shutdown?
  - How are we monitoring the performance of our service? Do we get alerts whenever critical components fail or their performance degrades?


