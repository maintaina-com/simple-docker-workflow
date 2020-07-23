# simple-docker-workflow

A simple docker workflow to demonstrate how to build a container image for docker/podman
using Github Actions.

Steps to reproduce the setup in this project:

1. If necessary, create a Github repository for your project.
2. Create a `Dockerfile`, commit it and push it. For a template file, see the one in this repository.
3. Navigate to the Actions tab. If this is not the first workflow in this repository, click "New Workflow"
4. Look for the workflow "Publish Docker Container" and click on "Set up this workflow"
5. Edit at least the name of the workflow and the image name.
6. Choose a suitable file name.
7. Commit the workflow.

Now Github will happily build your image and push it to its registry.

**Where do I find execution logs of workflows/jobs?**  
Click on the "Actions" tab. All workflows of your repository are shown on the left side. Choosing a workflow will show you the runs of that workflow. Choose a specific run to see the logs for each job in the run.

**Where do I find the created images?**  
To see the docker images of a repository, navigate to its packages page, e.g. the packages of this repository can be found [here](https://github.com/maintaina-com/simple-docker-workflow/packages). The packages page also has some starter instructions on how to use the image.

**How do I use the images?**  
Log into your Github Account and create a [Personal Access Token](https://github.com/settings/tokens) with the scope "read:packages". On your shell, run `docker login docker.pkg.github.com --username $YOUR_GITHUB_USERNAME` and enter this token as password. You may now pull the image or use in in your Dockerfiles.

Example for this repository:  
For commandline usage:
```bash
docker pull docker.pkg.github.com/maintaina-com/simple-docker-workflow/simple-docker:latest
```
or for a Dockerfile:
```Dockerfile
FROM docker.pkg.github.com/maintaina-com/simple-docker-workflow/simple-docker:latest
```
