---

title: Edit repository
description:
taxonomy:
    category: git-integration-for-jira-cloud

---

# Edit repository

<https://bigbrassband.atlassian.net/wiki/spaces/GITCLOUD/pages/1977384961/Edit+repository>

* * *

HOSTED EXTERNAL

On the Manage repositories page, click ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Actions ➜ **Edit repository** for the selected repository to open its repository configuration page where you can change the settings of the connected repository.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1977384961/gitcloud-edit-repo-cfg-single-repo.png?version=1&modificationDate=1648989722770&cacheVersion=1&api=v2)

Utilize the options below for configuring repository settings.

## Connection settings

|     |     |     |
| --- | --- | --- |
| **Option** | **Description** | **Repository type** |
| _**Enable this integration**_ | Toggle to enable/disable this repository for use with Jira. | SINGLE  <br>INTEGRATION |
| _**Display Name**_ | This is the alias that will appear in the Repository column. | SINGLE  <br>INTEGRATION |
| _**Repository Origin**_ | This is the URL path to a clone of the repository. | INTEGRATION |
| _**Username, Password/Token**_ | Displays username used for this repository configuration. Enter a new password/token if the password/token has changed since the last configuration. | SINGLE |
| _**Private SSH Key**_ | If the private SSH key was changed, enter the new private SSH key on the provided box or upload the new private SSH key. | SINGLE |
| _**Optional SSH Key Passphrase**_ | If the configured private SSH key has a passphrase, enter it on the provided box. | SINGLE |
| _**SSL Verify**_ | VSTS \| AZURE GITLAB GITHUB  <br>Set to enabled/disabled for the current git host integration.<br><br>The **SSL Verify** option is set to `Enabled` by default. If set to `Disabled`, the Git Integration for Jira app will ignore verification of SSL certificates when connecting to a git server.<br><br>The **SSL Verify** setting is available in Jira Server, Data Center and Jira Cloud. This option is not available for non-fetched repositories. | SINGLE |

## Feature settings

|     |     |     |
| --- | --- | --- |
| **Option** | **Description** | **Repository type** |
| _**Main Branch**_ | Set the main branch. The default setting is `master`. | SINGLE  <br>INTEGRATION |
| _**Indexing triggers**_ | Displays the indexing triggers URL for this repository. Click the adjacent copy icon to send the indexing triggers URL to the system clipboard. Use this URL to setup webhook to your git host service. | SINGLE  <br>INTEGRATION |
| _**Tags**_ | Set whether to show all tags or show on tags with matching regex pattern. For more information on git tags, see [Git tags](/wiki/spaces/GITCLOUD/pages/1923025983/Git+tags). | SINGLE  <br>INTEGRATION |
| _**Smart Commits & Workflow Triggers**_ | Enable/disable this setting to allows the users to use the [smart commits](/wiki/spaces/GITCLOUD/pages/1923025332/Smart+commits) feature. | SINGLE  <br>INTEGRATION |
| _**Project Permissions: Restrict to projects**_ | The default setting is **Associate with all projects**. You can restrict access to the Repository Browser and Git Commit tabs (Advanced) for the selected repository by [setting the project associations](/wiki/spaces/GITCLOUD/pages/1923024786/Associating+project+permissions). | SINGLE  <br>INTEGRATION |
| _**Web Linking**_ | _Optional._<br><br>The web linking feature adds links to your git hosting provider directly into the Git Commits tab. For special integrations (Auto-Connect), this feature is configured automatically. For more information on about this topic, see [Web linking](/wiki/spaces/GITCLOUD/pages/1923025184/Web+linking). | SINGLE |

Click **Save** to save the changes and apply the settings.

Click **Cancel** to return to the manage git configuration page and discard the changes.

[« Edit integration](/wiki/spaces/GITCLOUD/pages/1923024559/Edit+integration)

[SSL verify »](/wiki/spaces/GITCLOUD/pages/1923024654/SSL+Verify)

### More related topics about managing repository or integration configuration

*   Page:
    
    [Managing integration or repository configuration](/wiki/spaces/GITCLOUD/pages/1923024455/Managing+integration+or+repository+configuration) (Git Integration for Jira Cloud)
    
*   Page:
    
    [Managing integrations via Actions (Jira Cloud)](/wiki/spaces/GITCLOUD/pages/1923024517) (Git Integration for Jira Cloud)
    
*   Page:
    
    [Edit integration](/wiki/spaces/GITCLOUD/pages/1923024559/Edit+integration) (Git Integration for Jira Cloud)
    
*   Page:
    
    [SSL Verify](/wiki/spaces/GITCLOUD/pages/1923024654/SSL+Verify) (Git Integration for Jira Cloud)
    
*   Page:
    
    [Viewing indexing properties (Jira Cloud)](/wiki/spaces/GITCLOUD/pages/1923024741) (Git Integration for Jira Cloud)
    
*   Page:
    
    [Removing integration or repository configuration](/wiki/spaces/GITCLOUD/pages/1923024762/Removing+integration+or+repository+configuration) (Git Integration for Jira Cloud)
    
*   Page:
    
    [Associating project permissions](/wiki/spaces/GITCLOUD/pages/1923024786/Associating+project+permissions) (Git Integration for Jira Cloud)
    
*   Page:
    
    [Edit repository](/wiki/spaces/GITCLOUD/pages/1977384961/Edit+repository) (Git Integration for Jira Cloud)
    
*   Page:
    
    [View repository indexing logs](/wiki/spaces/GITCLOUD/pages/2013626625/View+repository+indexing+logs) (Git Integration for Jira Cloud)