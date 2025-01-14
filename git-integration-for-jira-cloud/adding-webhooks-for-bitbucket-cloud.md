---

title: Adding webhooks for Bitbucket Cloud
description:
taxonomy:
    category: git-integration-for-jira-cloud

---

# Adding webhooks for Bitbucket Cloud

<https://bigbrassband.atlassian.net/wiki/spaces/GITCLOUD/pages/467271681/Adding+webhooks+for+Bitbucket+Cloud>

* * *

Pull request webhooks are now supported. [See details](https://bigbrassband.atlassian.net/wiki/spaces/GITCLOUD/pages/467271681/Adding+webhooks+for+Bitbucket+Cloud#Pull-Request-Webhooks) on this page.

Supported webhook events:

*   _Repository_ - Push
    
*   _Pull request -_ Created
    
*   _Pull request_ - Updated
    

_Right-click_ [_here_](https://bigbrassband.wistia.com/medias/7tt09xc1my) _and view this video in a new browser tab._  
_(While the above video showcases other integration, jump to 01:41 to see Webhook setup for Bitbucket Cloud.)_

Before you can proceed with the steps outlined on this guide, webhooks must be enabled in the Git Integration for Jira app repository configuration for your Jira instance. For more details, see [**Indexing triggers - Getting Started**](https://bigbrassband.atlassian.net/wiki/spaces/GITCLOUD/pages/171475219/Webhooks).

## Setting up webhooks for Bitbucket Cloud

Configure webhook by logging in to your Bitbucket.

1.  Open a project by clicking on it.
    
2.  ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/467271681/webhooks-bitbucket-add-shooks(c).png?version=1&modificationDate=1588130532215&cacheVersion=1&api=v2&width=408&height=329)
    
    Click ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) **Repository Settings** then under **WORKFLOW**, select **Webhooks**.
    
3.  Click **Add webhook** to create a webhook for the repository. The _**Add new webhook**_ screen appears.
    
    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/467271681/webhooks-add-new-whook-bitbucket-dlg(w).png?version=1&modificationDate=1588130531394&cacheVersion=1&api=v2&width=578&height=759)
    1.  **Title** - This is the title name for this webhook.
        
    2.  **URL** - This field accepts the webhook url from your Git Integration for Jira app > **Webhooks** setting.
        
    3.  **Triggers** - By default, the trigger for the webhook is a repository push. If you want different actions to trigger the webhook, click _**Choose from a full list of triggers**_. The list of all the webhook trigger event types is displayed.  
        Set the necessary scope depending on your organization access/usage rules. For this guide, choose the following triggers:
        
        1.  Repository - **Push** (required)
            
        2.  Pull Request (optional) - select these options to also include the pull request triggers
            
            *   **Created**
                
            *   **Updated**
                
4.  Switch to your Jira instance then navigate to **Manage Git repositories** page and then click **Indexing triggers** (_or alternatively go to Jira Settings ➜ Apps. On the sidebar, click Indexing triggers_).
    
5.  ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/467271681/jira-cloud-webhook-url-loc(c1).png?version=1&modificationDate=1617191745969&cacheVersion=1&api=v2&width=646&height=430)
    
    Copy the complete secret key URL mentioned from the paragraph description below the **Secret key** box.
    
6.  Switch back to Bitbucket (where you left off) and paste this information into the provided **URL** box.
    
7.  Enter a meaningful **Title** name for this webhook.
    
8.  For the **Triggers**, if your organization does not require pull request events, select ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) **Repository push**. Otherwise, select _**Choose from a full list of triggers**_ (recommended) and then tick Repository (**Push**) and Pull Request (**Created**, **Updated**).
    
9.  Click **Save** to complete this setup.
    

## Pull request webhooks

The Git Integration for Jira app supports pull request webhooks now.

For pull request triggers, you will need to have three (3) separate service hooks configuration for it to work properly. See **step 9**, **second option** for the webhook triggers.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/467271681/webhooks-bitbucket-sample.png?version=1&modificationDate=1588130531945&cacheVersion=1&api=v2&width=680&height=195)