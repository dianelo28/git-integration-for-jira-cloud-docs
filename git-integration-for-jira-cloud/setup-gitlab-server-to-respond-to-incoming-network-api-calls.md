---

title: Setup GitLab Server to respond to incoming network API calls
description:
taxonomy:
    category: git-integration-for-jira-cloud

---

# Setup GitLab Server to respond to incoming network API calls

<https://bigbrassband.atlassian.net/wiki/spaces/GITCLOUD/pages/1923023297/Setup+GitLab+Server+to+respond+to+incoming+network+API+calls>

* * *

In order for GitLab to display correct repository clone links to your users, it needs to know the URL under which it is reached by your users (e.g. `http://gitlab.example.com`)

To reconfigure:

1.  Access the GitLab configuration file in `/etc/gitlab/gitlab.rb`.
    
    ```java
    sudo vi /etc/gitlab/gitlab.rb
    ```
    
2.  Change the `external_url` value to your GitLab server URL.
    
    ```java
    external_url "http://gitlab.example.com" #this is the default URL
    external_url "http://X.X.X.X.local/" #change it to your GitLab Server URL
    ```
    
3.  Run the reconfigure command to make the change take effect.
    
    ```java
    sudo gitlab-ctl reconfigure
    ```
    

  
Read this [**GitLab documentation**](https://docs.gitlab.com/omnibus/settings/configuration.html#configuring-the-external-url-for-gitlab) to know more about configuring the external URL for GitLab.

You should be able to add the GitLab repositories via Git Integration for Jira app ➜ Manage Git repositories:

*   **Full feature integration panel** (recommended for multiple repository integration)
    
*   **Connect to Git Repository** (single repository or SSH repository integration)
    
*   **Limited feature connect** (Git – single repository or SSH repository integration)
    

[« Getting started for Git administrators (index)](/wiki/spaces/GITCLOUD/pages/1923023183/Getting+started+for+Git+administrators)

[New GitLab v10+ authentication »](/wiki/spaces/GITCLOUD/pages/1923023311)

### More related topics about getting started for Jira admins

*   Page:
    
    [New GitLab v10+ authentication](/wiki/spaces/GITCLOUD/pages/1923023311) (Git Integration for Jira Cloud)
    
*   Page:
    
    [Setup GitLab Server to respond to incoming network API calls](/wiki/spaces/GITCLOUD/pages/1923023297/Setup+GitLab+Server+to+respond+to+incoming+network+API+calls) (Git Integration for Jira Cloud)
    
*   Page:
    
    [Setting up web linking](/wiki/spaces/GITCLOUD/pages/1923023467/Setting+up+web+linking) (Git Integration for Jira Cloud)
    
*   Page:
    
    [Setting up indexing triggers](/wiki/spaces/GITCLOUD/pages/1923023481/Setting+up+indexing+triggers) (Git Integration for Jira Cloud)