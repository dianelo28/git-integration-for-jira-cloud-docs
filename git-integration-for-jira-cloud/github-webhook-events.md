---

title: GitHub webhook events

description:
taxonomy:
    category: git-integration-for-jira-cloud

---

# GitHub webhook events

<https://bigbrassband.atlassian.net/wiki/spaces/GITCLOUD/pages/1921482779/GitHub+webhook+events>

* * *

The following are the supported types of GitHub events for triggering webhooks:

|     |
| --- |
| ### GitHub (Push Events) |
| _Type_  <br>**pushEvents:** `"^push$"` |
| _Request URI_  <br>`/api/1/webhook/reindex/install/`**<secret\_key>**`/web` |
| _Request headers_  <br>**Content-type:** `application/x-www-form-urlencoded`  <br>**X-GitHub-Event:** `push` |
| _Request payload example_<br><br>```java<br>*{<br>  ...<br>  "repository": {<br>    "id": 224819315,<br>    "git_url": "git://github.com/acme/test1.git",<br>    "ssh_url": "git@github.com:acme/test1.git",<br>    "clone_url": "https://github.com/acme/test1.git",<br>    "svn_url": "https://github.com/acme/test1",<br>  },<br>  ...<br>}<br>``` |

|     |
| --- |
| ### GitHub (Pull Request Events) |
| _Type_  <br>**pullRequestEvents:** `"^pull_request$"` |
| _Request URI_  <br>`/api/1/webhook/reindex/install/`**<secret\_key>**`/web` |
| _Request headers_  <br>**Content-type:** `application/x-www-form-urlencoded`  <br>**X-GitHub-Event:** `pull_request` |
| _Request payload_<br><br>```java<br>*{<br>  ...<br>  "repository": {<br>    "id": 224819315,<br>    "git_url": "git://github.com/acme/test1.git",<br>    "ssh_url": "git@github.com:acme/test1.git",<br>    "clone_url": "https://github.com/acme/test1.git",<br>    "svn_url": "https://github.com/acme/test1",<br>  },<br>  ...<br>}<br>``` |

|     |
| --- |
| ### GitHub (Repository Events) |
| Type  <br>**repositoryEvents:** "^repository$" |
| _Request URI_  <br>`/api/1/webhook/reindex/install/`**<secret\_key>**`/web` |
| _Request headers_  <br>**Content-Type:** `application/x-www-form-urlencoded`  <br>**X-GitHub-Event:** `repository` |
| _Request payload_<br><br>```java<br>*{<br>  ...<br>  "repository": {<br>    "id": 224819315,<br>    "git_url": "git://github.com/acme/test1.git",<br>    "ssh_url": "git@github.com:acme/test1.git",<br>    "clone_url": "https://github.com/acme/test1.git",<br>    "svn_url": "https://github.com/acme/test1",<br>  },<br>  ...<br>}<br>``` |

### Other webhook type events

*   Page:
    
    [GitHub webhook events](/wiki/spaces/GITCLOUD/pages/1921482779/GitHub+webhook+events) (Git Integration for Jira Cloud)
    
*   Page:
    
    [GitLab webhook events](/wiki/spaces/GITCLOUD/pages/1922465801/GitLab+webhook+events) (Git Integration for Jira Cloud)
    
*   Page:
    
    [Microsoft webhook events](/wiki/spaces/GITCLOUD/pages/1921876015/Microsoft+webhook+events) (Git Integration for Jira Cloud)
    
*   Page:
    
    [AWS CodeCommit webhook events](/wiki/spaces/GITCLOUD/pages/1922203671/AWS+CodeCommit+webhook+events) (Git Integration for Jira Cloud)
    
*   Page:
    
    [Bitbucket webhook events](/wiki/spaces/GITCLOUD/pages/1921548328/Bitbucket+webhook+events) (Git Integration for Jira Cloud)