## Gitpod Setup
This repository contains setup instructions for launching CVP repositories in a Gitpod ephemeral development environment.

### Getting Started
If you do not have a `gitpod.io` account create one and use the `Connect to Github` button to connect `gitpod.io` to your `github.com` account.
Please following the [Getting Started](https://www.gitpod.io/docs/introduction/getting-started) guide on the Gitpod website to create your account and get started.

### Account Setup
Once you have created your `gitpod.io` account, you will see a blank screen containing an empty workspace.

On the top left menu click "Projects" and then click the "New Project" button.

Select the dropdown and type "front" and then select this repo and click the "Create" button to create a project for this repository.
|  |  |
| --- | --- |
|  |  |

You should now have a project setup as shown below...

Select "Variables" in the left menu of the project and click the "New Variable" button.

Run `echo -n "ghcr.io:"; echo -n "your-github-username:your-pat-token" | base64 -w0` in bash and use the output for the "Value" below and then click "Add Variable".
| Name | Value |
| ---- | ----- |
| GITPOD_IMAGE_AUTH | ghcr.io:andfoaXlaGsfhZDc3OsdfdcF92bsdfxQQmrQfghlPbfgjhfgjWngyMFhxemw= |
|  |  |

> [!important]
> PAT Token is created via each user's developer settings and must have the `read:packages` permission in Github

### Running in Gitpod
You can now open any repository in Gitpod and begin developing. To open a repository in Gitpod append the Github repo url to the end of the Gitpod url. Example:  `https://gitpod.io/#https://github.com/cvpcorp/starter-kits-uswds-nextjs-page-router`

The startup will take a few minutes the first time and may require access to your github identity. Wait for the VSCode page to display, run tasks, and open ports. If you navigate to the ports tab in the lower section of the page, you should have ports 3000 (UI), 8080 (Keycloak), 8099 (PgAdmin), and 5432 (PGDB) and others depending on the project.

> [!note]
> - Run `gp env DOTENV="$(base64 .env | tr -d '\n')"` to persist .env file to $DOTENV
> - Run `echo "${DOTENV}" | base64 -d > .env` to restore .env file from $DOTENV
