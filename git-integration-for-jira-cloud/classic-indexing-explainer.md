---

title: Classic Indexing Explainer
description:
taxonomy:
    category: git-integration-for-jira-cloud

---


# Classic Indexing Explainer

<https://bigbrassband.atlassian.net/wiki/spaces/GITCLOUD/pages/183369754/Classic+Indexing+Explainer>

* * *

**What's on this page:**

* * *

The [**Git Integration for Jira Cloud**](https://marketplace.atlassian.com/4984) app automatically indexes commits, branches, tags, and pull/merge requests. Previously, all repositories and integrations were updated on a strict schedule – which is approximately every 8 minutes after the last indexing process has finished for an account. This worked for small accounts and provided consistency but was inefficient with large accounts (many with repositories that rarely change).

Starting on October 28, 2019, indexing is now calculated based on per repository activity. The overall goals are to reduce the strain on git services and make the indexing service more available for the webhook triggers.

**Note**  
Pull/merge requests are only indexed for repositories connected using the Full feature integrations panel in **Manage Git Repositories**. They can be accessed via the Jira Developer Panel on the right sidebar of a Jira issue. Git repositories added individually via SSH or HTTPS credentials will not show pull/merge requests.

## How is git data indexed?

Git Integration for Jira Cloud indexes a variety of Git and Git related data once connected by a Jira administrator. The table below describes how each data type is accessed. All data is stored until a Jira administrator removes the integration or the subscription is cancelled or expires.

See our [Privacy Policy](https://bigbrassband.com/privacy-policy.html) and [Data Deletion Policy](https://bigbrassband.com/security.html).

|     |     |
| --- | --- |
| **Data Type** | **Method** |
| Commits | Git clone |
| Branches | Git clone |
| Tags | Git clone |
| Pull requests | API |
| Merge requests | API |
| List of repositories | API |

## Automatic indexing

### Indexing repositories

An internal process runs approximately every 8 minutes to review repositories eligible to be checked for changes. All repositories are checked for changes at least once daily. A repository change (commit, branch, tag) will cause the _Next repository check_ to be calculated next: in a quarter of the time since the last repository update was detected.

For example, if the last commit was detected 4 hours ago then the _Next repository check_ will be scheduled in 1 hour.

The time for _Next repository check_ are re-calculated on each indexer check.

### Indexing integrations

An internal process runs approximately every 8 minutes to review integrations eligible to be checked for changes. Integrations (for example, GitLab, GitHub, etc) are checked during each _Next indexer check_ via the git service's API for available repositories. 

All repositories are checked for changes at least once daily. A repository change (commit, branch, tag) will cause the _Next repository check_ to be calculated next: in a quarter of the time since the last repository update was detected.

For example, if the last commit was detected 4 hours ago then the _Next repository check_ will be scheduled in 1 hour.

_Next repository check_ times are re-calculated on each indexer check.

### Triggering automatic reindexes via webhooks

Automatic indexing is designed to record changes in a timely manner for all types of repositories, but ideally, changes should be indexed immediately. Configuring webhooks to trigger automatic reindexing will result in immediate reindex times.

When webhooks are received by the indexing service, the indexing service will reduce the automatic indexing to once - hourly.

For more information on configuring webhooks, see: [Indexing triggers](/wiki/spaces/GITCLOUD/pages/171475219/Indexing+Triggers).

### Automatic indexing period limits

The table below describes the automatic indexing period limits:

|     |     |     |     |
| --- | --- | --- | --- |
| **Action** | **Conditions** | **Min. period** | **Max. period** |
| Check a repository | No webhook (PR or push) arrives for the repository | 450 secs | 24 hr |
| Check a repository | Webhooks (PR or push) arrives for the repository | 1 hr | 24 hr |
| Check an integration | Regardless of arriving webhooks | 19.2 hrs | 24 hr |

If the indexing has been requested by a user or a webhook, it will be executed immediately – regardless of any skipping settings.

There can be an additional delay with repository indexer checking due to fetch delay.

## Manual indexing

### Reindex all

All repositories and integrations can be updated manually via the Manage Git repositories screen by selecting the **Reindex All** button:

![Git Cloud manage git repositories page highlighting Reindex All](https://bigbrassband.atlassian.net/wiki/download/attachments/183369754/gitcloud-reindex-all-iex.png?version=1&modificationDate=1598591995427&cacheVersion=1&api=v2)

### Repositories

Repositories can be updated manually via the Manage git repositories screen by opening the ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Actions menu and selecting **Reindex repository**:

![Git Cloud manage git repositories page highlighting Reindex repository action](https://bigbrassband.atlassian.net/wiki/download/attachments/183369754/gitcloud-reindex-repo-iex.png?version=1&modificationDate=1598591995919&cacheVersion=1&api=v2)

### Integrations 

Integrations can be updated manually via the Manage git repositories screen by opening the ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Actions menu and selecting **Reindex integration**:

![Git Cloud manage git repositories page highlighting Reindex integration action](https://bigbrassband.atlassian.net/wiki/download/attachments/183369754/gitcloud-reindex-integration-iex.png?version=1&modificationDate=1598591996399&cacheVersion=1&api=v2)

### Indexing statuses

|     |     |
| --- | --- |
| Status | Description |
| INDEXED | Integration or repository has been indexed and no errors were detected. |
| QUEUED | Integration or repository is actively queued for indexing. |
| INDEXING | Indexer is actively checking integration or repository for changes. |
| ERROR | Integration has at least one repository in an error state (and not updating) and at least one repository was successfully updated. |
| ERROR | Integration or all repositories are in an error state and are not updating. |

## Indexing definitions 

The [**Git Integration for Jira**](https://marketplace.atlassian.com/4984) app now has new indexing date/times to indicate the variety of repository checks:

![Show tracked repos action dialog showcasing indexing definitions](https://bigbrassband.atlassian.net/wiki/download/attachments/183369754/gitcloud-indexing-defs.png?version=1&modificationDate=1598591997067&cacheVersion=1&api=v2)

### Definitions

|     |     |
| --- | --- |
| **Information Label** | **Description** |
| _Last indexer check_ | Date and time the indexing service has checked if the repository should be examined for changes. |
| _Next indexer check_ | Date and time the indexing service will next check if the repository should be examined for changes (commits, tags, branches) |
| _Last repository check_ | Date and time the indexing service has last checked the repository for changes (commits, tags, branches) |
| _Last repository change_ | Date and time the indexing service last detected a change (commits, tags, branches) in the repository. This time is accurate only as of the release of the new indexing service on October 27, 2019 or when the repository was first integrated with Git Integration for Jira Cloud. |
| _Next repository check_ | Date and time the indexing service will check the repository for changes (commits, tags, branches). |
| _Commit webhooks detected_ | Indexing service has received a commit webhook trigger for this repository. Thus, automatic indexing for this repository is reduced to once daily. |
| _Last pull request check_ | Date and time the indexing service last checked the repository for pull request changes (new pull/merge requests or status changes). |
| _Last pull request change_ | Date and time the indexing service last detected a change (new pull/merge requests or status changes) in the repository. This time is accurate only as of the release of the new indexing service on October 27, 2019. |
| _Next pull request check_ | Date and time the indexing service will check repository for new pull/merge requests or status changes. |
| _Pull request webhooks detected_ | Indexing service has received a pull/merge request webhook trigger for this repository. Thus, automatic indexing for this repository is reduced to once hourly. |

The upper limit of the indexer checking frequency is daily (24 hours / 86400 seconds). The integration and repository indexer checking upper limit follows the same value.

### Indexing errors

![Git commits tab in Jira issue showing indexing error messages](https://bigbrassband.atlassian.net/wiki/download/attachments/183369754/image-20200828-050318.png?version=1&modificationDate=1598591997511&cacheVersion=1&api=v2)

**Indexing Errors**  
A notification about indexing error is displayed in the Git Commits tab so that Jira administrators can be alerted immediately.

If you still have a question – reach out to our [**Support Desk**](https://bigbrassband.atlassian.net/servicedesk/customer/portals) or email us at [support@bigbrassband.com](mailto:support@bigbrassband.com).

## Branch and pull/merge request name index triggers

Pull/merge requests are still indexed based on branch name even if the PR/MR title does not have the Jira issue key – as long as the branch name contains the Jira issue key.