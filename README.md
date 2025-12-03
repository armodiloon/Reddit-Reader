# Reddit Story Fetcher

This is a simple personal-use script that fetches text posts from specific subreddits using Reddit's API.  
It is used to analyze text, generate summaries, and experiment with audio narration tools.


```python
import praw

reddit = praw.Reddit(
    client_id="CLIENT_ID",
    client_secret="CLIENT_SECRET",
    user_agent="story-fetcher by u/YOUR_USERNAME"
)

sub = reddit.subreddit("TrueOffMyChest")

for post in sub.top(time_filter="week", limit=10):
    if post.selftext:
        print(post.title)
        print(post.selftext[:200], "...")
        print()
