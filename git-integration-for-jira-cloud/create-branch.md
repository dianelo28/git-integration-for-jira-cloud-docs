---

title: Create branch
description:
taxonomy:
    category: git-integration-for-jira-cloud

---


# Create branch

<https://bigbrassband.atlassian.net/wiki/spaces/GITCLOUD/pages/733282366/Create+branch>

* * *

  

**Jira administrator notes**

*   Jira users can now provide their own personal access tokens (PAT) even if they are not required/mandated by the Jira admin. See [Require Personal Access Tokens for user actions (create branch/pull request)](/wiki/spaces/GITCLOUD/pages/131137621) for instructions on how to configure this feature.
*   The **View developer tools** _permission_ is required to view the Source Code panel (see more in [Issue Git Source Code Panel](/wiki/spaces/GITCLOUD/pages/138346503/Issue+Git+Source+Code+Panel)). Jira users must also have the **Browse Project** _permissions_ to a project associated with a repository to view.
*   Creating branch feature can be disabled for all Jira users (regardless of permissions) in General settings

  

* * *

  

## **Introduction**

The Create branch feature offers Jira users the ability to create a git branch directly from the Jira issue.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/733282366/gitcloud-create-branch-dlg.png?version=1&modificationDate=1635931446719&cacheVersion=1&api=v2)

  
For information about creating pull/merge requests from a Jira issue - see [Create pull or merge request](/wiki/spaces/GITCLOUD/pages/733315235/Create+pull+or+merge+request).

## **Advantages**

When creating a branch from within Jira: 

*   Automatically populates branch name with issue key (necessary for branch ↔ issue association) and issue summary.
*   Further - default branch naming conventions can be customized to match your development workflow.  For example: `${issuetype:New Issue,new,Bug Fix,bug}/${issuekey}-${summary}` generates "`bug/PRJ-123-add-more-logging`" (See General settings for more information).
*   Require each Jira user to provide their Personal Access Token for creating branches.  This option adds some friction to creating branches/pull requests but enabling this setting will enforce the git server user permissions as well as give better attribution for the actions.  See [Require Personal Access Tokens for user actions (create branch/pull request)](/wiki/spaces/GITCLOUD/pages/131137621) for more information.
*   Each Jira user can set a **Default repository** for the current Jira project. (See User settings for more information).

  

## **Supported**

*   Full feature integrations:
    *   GitHub
    *   GitLab
    *   Bitbucket Cloud
    *   AWS CodeCommit
    *   Azure DevOps
    *   Microsoft Visual Studio Team Services (VSTS)
    *   Microsoft Team Foundation Server (TFS)
*   Supported in the Atlassian Jira Cloud [iOS](https://www.atlassian.com/software/jira/mobile-app), [Android](https://www.atlassian.com/software/jira/mobile-app) and [MacOS](https://www.atlassian.com/software/jira/mac).
*   Company-managed and Team-managed Jira projects supported.
*   New and old Jira Issue View supported.

  

## **Steps to creating a git branch in Jira**

1.  **Prerequisite:** Jira administrator configures a Full feature integration in the Git Integration for Jira Cloud app. See [Integration Guide](/wiki/spaces/GITCLOUD/pages/82378780/Integration+Guide) for more information.
2.  To access the Create branch action - do one of the following:
    1.  Enable the **Git Development panel** or
    2.  Open the [Issue Git Source Code Panel](/wiki/spaces/GITCLOUD/pages/138346503/Issue+Git+Source+Code+Panel)
3.  Click **Create branch** in one of the panels from step 2.
4.  Select git repository.
    1.  Optional: designate the repository to be the default selected repository for current Jira project. To configure default repositories for more than one Jira project - use the [User settings](/wiki/spaces/GITCLOUD/pages/781975665/User+Settings) page.
    2.  Use the search box to look for the specific name of the repository that will be used.
5.  If a [personal access token is required](/wiki/spaces/GITCLOUD/pages/131137621) (and not yet provided) - follow on screen instructions to provide a [personal access token](/wiki/spaces/GITCLOUD/pages/107216897/Creating+Personal+Access+Tokens) with correct permissions for selected repository.
6.  Select base branch.
7.  Verify branch name is correct. Edit as desired. Note: the Jira issue key must remain in the branch name to create the branch ↔ Jira issue association.
8.  Click **Create branch**.

  

**Video: **Creating branch from** Git Development panel**

  

_Right click_ [_here_](https://bigbrassband.wistia.com/medias/8cy7v6ykug) _to open this video in a new browser tab for more viewing options._

  

**Video: Creating branch from Git Source Code panel**

  

_Right click_ [_here_](https://bigbrassband.wistia.com/medias/2re05azbwl) _to open this video in a new browser tab for more viewing options._

  

  

If you still have a question - reach out to our [Support Desk](https://bigbrassband.atlassian.net/servicedesk/customer/portals) or email us at [support@bigbrassband.com](mailto:support@bigbrassband.com).