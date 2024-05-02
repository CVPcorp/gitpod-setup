## Gitpod Setup
This repository contains setup instructions for launching CVP repositories in a Gitpod ephemeral development environment.

### Getting Started
If you do not have a `gitpod.io` account create one and use the `Connect to Github` button to connect `gitpod.io` to your `github.com` account.
Please following the [Getting Started](https://www.gitpod.io/docs/introduction/getting-started) guide on the `Gitpod` website to create your account and get started.

### Account Setup
Once you have created your `gitpod.io` account and logged in, you will see a screen containing an empty workspace. In the top left, click the dropdown with your name to the left of `Workspaces` and select `Respository Settings`.
![image](https://github.com/CVPcorp/gitpod-setup/assets/66504934/2941173f-af31-4c3f-9fd7-badcf08b4f10)

Click the `Add a Repository` button to add a repository of your choice.

![image](https://github.com/CVPcorp/gitpod-setup/assets/66504934/189f4539-8eb7-4b26-8e63-fcffd46ef78d)

In the dropdown, type the first 3 or 4 characters of the name of the repository you want to add and select it from the list once it appears.
![image](https://github.com/CVPcorp/gitpod-setup/assets/66504934/ef1e035d-e438-4a21-83e5-dc5882744821) |

Select the repository from the list and click the `Add` button.

![image](https://github.com/CVPcorp/gitpod-setup/assets/66504934/1da26868-42ae-4d45-bca8-a6653b1d46f1)

You should now have a project setup as shown below...

Select "Variables" in the left menu of the project and click the "New Variable" button.

Run `echo -n "ghcr.io:"; echo -n "your-github-username:your-pat-token" | base64 -w0` in bash and use the output for the "Value" below and then click "Add Variable".
| Name | Value |
| ---- | ----- |
| GITPOD_IMAGE_AUTH | ghcr.io:andfoaXlaGsfhZDc3OsdfdcF92bsdfxQQmrQfghlPbfgjhfgjWngyMFhxemw= |

> [!important]
> PAT Token is created via each user's developer settings and must have the `read:packages` permission in Github

### Running in Gitpod
You can now open any repository in Gitpod and begin developing. To open a repository in Gitpod append the Github repo url to the end of the Gitpod url.
Example:  `https://gitpod.io/#https://github.com/cvpcorp/starter-kits-uswds-nextjs-page-router`

The startup will take a few minutes the first time and may require access to your github identity. Wait for the VSCode page to display, run tasks, and open ports. If you navigate to the ports tab in the lower section of the page, you should have ports 3000 (UI), 8080 (Keycloak), 8099 (PgAdmin), and 5432 (PGDB) and others depending on the project.

If you get the following error make sure the GITPOD_IMAGE_AUTH environment variable has been setup as discussed above in the Account Setup section. Otherwise, contact your organization admin to ensure you have read access to the Image Harbor repository that houses the Gitpod workspace image.

![image](https://github.com/CVPcorp/gitpod-setup/assets/66504934/c8fafd6b-7f30-4335-a517-c63637374131)

> [!note]
> - Run `gp env DOTENV="$(base64 .env | tr -d '\n')"` to persist .env file to $DOTENV
> - Run `echo "${DOTENV}" | base64 -d > .env` to restore .env file from $DOTENV
