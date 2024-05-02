## Gitpod Setup
This repositiry contains setup instructions for launching CVP repositories in a Gitpod ephemeral development environment. If you do not have a `gitpod.io` account create one and use the `Connect to Github` button to connect `gitpod.io` to your `github.com` account. Please following the [Getting Started](https://www.gitpod.io/docs/introduction/getting-started) guide on the Gitpod website to create your account and get started.

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
