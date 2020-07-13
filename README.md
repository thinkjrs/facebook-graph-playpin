# facebook-graph-playpin
Various items describing the Facebook graph api.

## What is a graph api?

Graphql.org has a [fanstastic overview site](https://graphql.org/learn/). For a different learning experience, [howtographql](https://www.howtographql.com/) has a full hour-long course series on GraphQL in addition to language-specific library overviews.

## Facebook Marketing API

### Campaigns
Campaigns are described in the docs as the single-objective group of ad-sets.

#### By account
The below should get the account's list of running campaigns:
##### Raw query:
```sh
act_<longnumberfbgivesyou>?fields=campaigns
```
##### Returns:
```json
{
  "campaigns": {
    "data": [
      {
        "id": "<longnumberfbgivesyou>"
      }
    ],
    "paging": {
      "cursors": {
        "before": "base64encodedHash",
        "after": "base64encodedHash"
      },
      "next": "https://graph.facebook.com/v7.0/act_<longnumberfbgivesyou>/campaigns?access_token=..."
    }
  },
  "id": "act_<longnumberfbgivesyou>"
}
```
#### Get all the campaigns for a given ad-account
##### Raw query:
```shell
act_<longnumberfbgivesyou>/campaigns
```
##### Returns:
```json
{
  "data": [
    {
      "id": "<longnumberfbgivesyou>"
    },
    {
      "id": "<longnumberfbgivesyou>"
    },
    {
      "id": "<longnumberfbgivesyou>"
    },
  ],
  "paging": {
    "cursors": {
      "before": "base64encodedHash",
      "after": "base64encodedHash"
    }
  }
}
```
#### Get specific campaign data
This should return the ids, account id, spend and impressions, among other items.

##### Raw query:
```shell
<longnumberfbgivesyou>/insights
```
##### Returns:
```json
{
  "data": [
    {
      "account_id": "<longnumberfbgivesyou>",
      "campaign_id": "<longnumberfbgivesyou>",
      "date_start": "2020-06-13",
      "date_stop": "2020-07-12",
      "impressions": "937",
      "spend": "2.04"
    }
  ],
  "paging": {
    "cursors": {
      "before": "base64encodedHash",
      "after": "base64encodedHash"
    }
  }
}
```
#### Get specific - Campaign ads
The below returns the actual ads under that campaign.

##### Raw query:
```sh
<longnumberfbgivesyou>/ads
```
##### Returns:

```json
{
  "data": [
    {
      "id": "<longnumberfbgivesyou>"
    },
    {
      "id": "<longnumberfbgivesyou>"
    },
    {
      "id": "<longnumberfbgivesyou>"
    },
  ],
  "paging": {
    "cursors": {
      "before": "base64encodedHash",
      "after": "base64encodedHash"
    }
  }
}
```

### Ads
Get detailed information on each specific ad for each specific campaign

#### By account
The below should get the account's list of running ads:
##### Raw query:
```sh
act_<longnumberfbgivesyou>?fields=ads
```
##### Returns:
```json
{
  "ads": {
    "data": [
      {
        "id": "<longnumberfbgivesyou>"
      }

    ],
    "paging": {
      "cursors": {
        "before": "base64encodedHash",
        "after": "base64encodedHash"
      },
      "next": "https://graph.facebook.com/v7.0/act_<longnumberfbgivesyou>/ads?access_token=..."
    }
  },
  "id": "act_<longnumberfbgivesyou>"
}
```
