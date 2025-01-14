---

title: Setting Project Permissions
description:
taxonomy:
    category: git-integration-for-jira-cloud

---

# Setting Project Permissions

<https://bigbrassband.atlassian.net/wiki/spaces/GITCLOUD/pages/509509708/Setting+Project+Permissions>

* * *

**What’s on this page:**

* * *

## Introduction

By default - integrations (GitLab, GitHub, etc) and individual repositories are associated with all Jira projects. Jira administrators can limit which Jira projects are associated to integrations or individual repositories.

**Related Features**  
Associating a Jira project with an integration or repository will limit repository content displaying in:

*   **Git Commits** issue tab
    
*   **Git Roll Up** issue tab
    
*   **Git Source Code** issue side panel 
    
*   **View all repositories** page
    
*   **Repository Browser: Browse** page
    
*   **Repository Browser: Commits** page
    
*   **Repository Browser: Compare** page
    
*   **Create branch issue** dialog
    
*   **Create pull/merge request** issue dialog
    

Jira users must have the **View Development Tools** permission in the context of a Jira project to view content from the Git Integration for Jira app.

## Instructions for integrations (GitLab, GitHub, etc)

To limit which Jira projects are associated with an integration's repositories:

1.  Navigate to menu **Git** > **Manage Git repositories.**
    
2.  Add a new integration or edit existing integration's settings.
    
3.  Locate the **Project Permissions** setting.
    
4.  Uncheck **Associate with all projects.**
    
5.  Select one or more Jira projects (at least one must be selected).
    
6.  Click **Update.**
    

### **Video Example 1:** Setting project permissions for an existing GitLab integration

_Right click_ [_here_](https://bigbrassband.wistia.com/medias/rnm5t639cz) _to open this video in a new browser tab for more viewing options._

### **Video Example 2:** Setting project permissions at the repository level for an existing GitLab integration

_Right click_ [_here_](https://bigbrassband.wistia.com/medias/fder2qnpgw) _to open this video in a new browser tab for more viewing options._

## Instructions for individual repositories

To limit which Jira projects are associated for individual repositories:

1.  Navigate to menu **Git** > **Manage Git repositories.**
    
2.  Add a new repository or edit existing repository's settings.
    
3.  Locate the **Project Permissions** setting.
    
4.  Uncheck **Associate with all projects.**
    
5.  Select one or more Jira projects (at least one must be selected).
    
6.  Click **Update.**
    

### **Video Example:** Setting project permissions for a repository 

_Right click_ [_here_](https://bigbrassband.wistia.com/medias/xvzj32nxou) _to open this video in a new browser tab for more viewing options._

## Related articles

*   Page:
    
    [Require Personal Access Tokens for user actions (create branch/pull request)](/wiki/spaces/GITCLOUD/pages/131137621) (Git Integration for Jira Cloud)
    
*   Page:
    
    [Permissions](/wiki/spaces/GITCLOUD/pages/405962836/Permissions) (Git Integration for Jira Cloud)
    
*   Page:
    
    [Setting Project Permissions](/wiki/spaces/GITCLOUD/pages/509509708/Setting+Project+Permissions) (Git Integration for Jira Cloud)
    
*   Page:
    
    [Trusted Users](/wiki/spaces/GITCLOUD/pages/792002572/Trusted+Users) (Git Integration for Jira Cloud)