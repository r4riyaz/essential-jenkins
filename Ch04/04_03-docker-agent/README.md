# 04_03 Docker agent
## Run a pipeline using a Docker agent.
## Requirments:
  - Jenkins may need more disk space and RAM
  - Install Docker as a service
  - Install the Docker Pipeline Plugin

## Create a new pipeline project in your Jenkins server.
  - Install Docker Pipeline Plugin.
  - Select `New Item`
  - Enter item name (use the same name as your repo if possible)
  - Select `Pipeline` project
  - `OK`
  - Select `GitHub Project` and paste in the repo URL `https://github.com/r4riyaz/essential-jenkins.git`
    - *NOTE: This step is optional.  It only creates a link to the repo on the project home page.*
  - Under `Pipeline`, select `Pipeline script from SCM`.
  - Under SCM, select `Git`.
  - Under `Repository URL`, paste in the repo URL `https://github.com/r4riyaz/essential-jenkins.git`
  - Under `Branch Specifier (blank for 'any')`, change `master` to `main`.
  - Under `Script Path` mention `Ch04/04_03-docker-agent/Jenkinsfile`
  - `Save` &rarr; `Build Now`
