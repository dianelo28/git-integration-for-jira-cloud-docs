---

title: Working with Custom API Path
description:
taxonomy:
    category: git-integration-for-jira-cloud

---

# Working with Custom API Path

<https://bigbrassband.atlassian.net/wiki/spaces/GITCLOUD/pages/133201972/Working+with+Custom+API+Path>

* * *

The Custom API Path is a relative path that starts with "/". The maximum allowed length is **2000** characters. The integration will use the relative REST API path to retrieve the list of tracked repositories.

The Custom API Path is called in the integration setup, settings changes, on a regular scheduled reindex and for a manual reindex.

**What’s on this page:**

* * *

## Accessible Locations

|     |
| --- |
| *   Go to Manage Git repositories page ➜ Full feature integration wizard ➜ **Connect** screen ➜ _Advanced_ ➜ **Custom API Path**. In this case, we use GitHub as an example: |
| ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/133201972/gitcloud-autoconnect-github-custom-api-path.png?version=1&modificationDate=1638348182666&cacheVersion=1&api=v2&width=566&height=510) |

|     |
| --- |
| *   Go to Manage Git repositories page ➜ ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Actions ➜ Edit integration settings (for integration) or Edit repository settings (for repositories) ➜ Integration settings section ➜ **Custom API Path**. |
| ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/133201972/gitcloud-actions-edit-integration-settings-cAPI-path.png?version=1&modificationDate=1638348403238&cacheVersion=1&api=v2&width=566&height=211) |

* * *

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/133201972/github-mobile.png?version=2&modificationDate=1638349121901&cacheVersion=1&api=v2&width=56&height=56)

## GitHub.com examples

|     |
| --- |
| **1\. Lists all repositories (default)** |
| ```java<br>/user/repos<br>``` |
| Gets a list of repositories. This is the same as when no API path is specified. |

|     |
| --- |
| **2\. Display all repositories from <username>** |
| ```java<br>/users/<username>/repos<br>``` |
| Gets a list of public repositories for the specified user, **<username>**.<br><br>For example: `/users/johnsmith/repos` |

|     |
| --- |
| **3\. Displays starred repositories** |
| ```java<br>/user/starred<br>``` |
| Gets the list of starred repositories for the authenticated user. |
| ```java<br>/users/<username>/starred<br>``` |
| Gets the list of starred public/private repositories for the specified user, **<username>**.<br><br>For example: `/users/johnsmith/starred` |

|     |
| --- |
| **4\. List all repositories for the specified organization** |
| ```java<br>/orgs/<org>/repos<br>``` |
| Gets a list of repositories for the specified org, **<org>**. _BigBrassBand_<br><br>_**For instance:**_<br><br>```java<br>/orgs/BigBrassBand/repos<br>```<br><br>This will filter for repositories only within the org: BigBrassBand. This works for GitHub.com integrations. |

* * *

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/133201972/github-ent-64.png?version=1&modificationDate=1638349289767&cacheVersion=1&api=v2&width=56&height=54)

## GitHub Enterprise examples

|     |
| --- |
| **1\. Lists all repositories (default)** |
| ```java<br>/api/v3/user/repos<br>``` |
| Gets the list of starred repositories for the authenticated user. |

|     |
| --- |
| **2\. Display all repositories from <username>** |
| ```java<br>/api/v3/users/<username>/repos<br>``` |
| Gets a list of public repositories for the specified user, **<username>**.<br><br>For example: `/api/v3/users/johnsmith/repos` |

|     |
| --- |
| **3\. Display starred repositories** |
| ```java<br>/api/v3/user/starred<br>``` |
| Gets the list of starred repositories for the authenticated user. |
| ```java<br>/api/v3/users/<username>/starred<br>``` |
| Gets the list of public/private starred repositories for the specified user, **<username>**.<br><br>For example: `/api/v3/users/johnsmith/starred` |

|     |
| --- |
| **4\. List all repositories for the specified organization** |
| ```java<br>/api/v3/orgs/<org>/repos<br>``` |
| Gets a list of repositories for the specified org, **<org>**. _BigBrassBand_<br><br>_**For instance:**_<br><br>```java<br>/api/v3/orgs/BigBrassBand/repos<br>```<br><br>This will filter for repositories only within the org: BigBrassBand. This works for GitHub Enterprise integrations. |

* * *

![](https://bigbrassband.atlassian.net/wiki/download/attachments/133201972/gitlab-mobile.png?version=1&modificationDate=1638351658250&cacheVersion=1&api=v2)

## GitLab.com | GitLab CE/EE examples

|     |
| --- |
| **1\. Lists all projects (default)** |
| ```java<br>/api/v4/projects?membership=true<br>``` |
| Gets a list of projects. This is the same as when no API path is specified. |

|     |
| --- |
| **2\. Display all projects from <user\_id>** |
| ```java<br>/api/v4/users/<user_id>/projects<br>``` |
| Gets a list of projects for the specified user, **<user\_id>**.<br><br>For example: `/api/v4/users/johnsmith/projects` |

|     |
| --- |
| **3\. Displays starred projects** |
| ```java<br>/api/v4/projects?starred=true<br>``` |
| Returns GitLab projects that have been starred by the connecting GitLab user. |

|     |
| --- |
| **4\. Limit to owned projects** |
| ```java<br>/api/v4/projects?owned=true<br>``` |
| The current user will be limited to the projects it's explicitly owned. |

|     |
| --- |
| **5\. List projects from within a Group** |
| ```java<br>/api/v4/groups/5245789/projects<br>/api/v4/groups/BigBrassBand/projects<br>``` |
| Returns the list of repositories within a GitLab Group (or GitLab Subgroup).<br><br>In the above examples, you can use the **Group id** or your **Group** **name** as query parameter. |

|     |
| --- |
| **6\. List projects from the specified sub-group** |
| ```java<br>/api/v4/groups/5245789/projects?include_subgroups=true<br>/api/v4/groups/BigBrassBand/projects?include_subgroups=true<br>``` |
| In the above examples, the _**?include\_subgroups=true**_ API extension will return a recursive list of repositories within a nested GitLab Group (or GitLab Subgroup) where the #, **5245789**, is the **Group id**; and **BigBrassBand** is the **Group name**. |

For more information on GitLab custom API paths, see [**GitLab API**](https://docs.gitlab.com/ee/api/projects.html).

**GitLab version API support:**  
Gitlab v9.5 and above -- only API v4  
Gitlab v9.0 to v9.4.x -- API v3 and API v4

**Remember:**  
The GitLab.com API can see all the public projects. For GitLab.com, we recommend using JMESPath over the Custom API path when possible. For more information, see [Working with JMESPath filters](/wiki/spaces/GITCLOUD/pages/133234759/Working+with+JMESPath+Filters).

* * *

![](https://bigbrassband.atlassian.net/wiki/download/attachments/133201972/bitbucket-mobile.png?version=1&modificationDate=1638352041213&cacheVersion=1&api=v2)

## Bitbucket Cloud examples

|     |
| --- |
| **1\. Lists all repositories for the specific user (default)** |
| ```java<br>/!api/2.0/repositories/<username><br>``` |
| Displays a list of git repositories of the user with the specified username. This is the same as when no API path is specified.<br><br>**For example:**<br><br>```java<br>/!api/2.0/repositories/wcoyote<br>``` |

|     |
| --- |
| **2\. Lists all repositories for the specified workspace ID** |
| ```java<br>/!api/2.0/repositories/<workspaceID><br>``` |
| Displays a list of git repositories for the specified workspace ID.<br><br>**For example:**<br><br>```java<br>/!api/2.0/repositories/acmegroup<br>``` |

While Custom API Path and JMESPath filter are mutually exclusive, you can use one, the other, both or neither.

* * *

_1 Logo owned by_ [_GitLab Inc_](https://gitlab.com/) _used under_ [_license_](https://creativecommons.org/licenses/by-nc-sa/4.0/)