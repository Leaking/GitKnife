# GitKnife
An Android library for Github API,I have use it in [WeGit](https://github.com/Leaking/WeGit).

# About The Github API

You can read the API documents in [https://developer.github.com/v3/](https://developer.github.com/v3/).



# Rate Limiting
Without authorizations,the rate limiting is 60 per minute,With authorizations,the rate limiting is 5000 per minute.So you had better add token in your every request.


# Token
In the latest API,you can not get existing token,so if you want to get existing token you need to delete it and re-create it.


# How to use it



## Init

```java
Github github = new GithubImpl(context);
```

## Create Token

```java
String token = github.createToken(username,password);
```

## Get Login User

```java
User user = github.authUser(token);
```

## Get Certain User

```java
User user = github.user(username);
```

## Repositories

```java
repos = github.repo(user, page);                  
```

## Starred Repositories

```java
repos = github.starred(user, page);
```

## Followings

```java
users = github.follwerings(user, page);
```

## Your Followers

```java
users = github.followers(user, page);
```

## If you has followed someone

```java
github.makeAuthRequest(token);
boolean ifFollow = github.hasFollow(targetUser);
```

## Unfollow someone

```java
github.makeAuthRequest(token);
boolean success = github.unfollow(targetUser);
```

## Follow someone

```java
github.makeAuthRequest(token);
boolean success = github.follow(targetUser);
```

## If you has starred Repo X

```java
boolean hasStar = github.hasStarRepo(owner, repo);
```

## Star Repo X

```java
github.makeAuthRequest(token);
boolean success = github.starRepo(owner, repo);
```

## Unstar Repo X

```java
github.makeAuthRequest(token);
boolean success = github.unStarRepo(owner, repo);


## Received Event

```java
events = github.receivedEvent(user, page);
```

## Stargzers of Repo X

```java
users = github.stargazers(owner,repo,page);
```

## Forkers of Repo X

```java
users = github.forkers(owner,repo,page);
```

## Load content of Repo X

```java
Tree tree  = github.getTree(owner, repo, sha);
```
