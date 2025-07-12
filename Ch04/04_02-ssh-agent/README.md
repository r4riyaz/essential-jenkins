# 04_02 SSH agent
## Connect to a node via SSH.
## Requirments:
  - Server that is accessible from jenkins.
  - User account and SSH key

## Steps to Configure SSH agent:
  - Select `Manage Jenkins` &rarr; `Nodes`
  - Select `New Node` &rarr; Enter `Node Name` and Select `Type` &rarr; `Permnanent Agent` &rarr; `Create`
  - Enter `Remote root directory` as Home directory of user from which we're accessing node via SSH.
  - `Labels` &rarr; `linux`
  - `Usage` &rarr; `Only build jobs with label expressions matching this node`
  - `Launch Method` &rarr; `Launch agents via SSH`
    - `Host` &rarr; "IP or Hostname"
    - `Credentials` &rarr; `Add`
       - `Kind` &rarr; `SSH Username with Private Key`
       - `ID` &rarr; `linux`, `Descrption` &rarr; `linux`
       - `username` &rarr; `ubuntu` ....(or any user from which the SSH connection will be made)
       - Add private key
    - `Credentials` &rarr; `Select Created credentials`
    - `Host Key Verification Strategy` &rarr; `Non verifying Verification Strategy`
  - `Availibility` &rarr; `Keep this agent online as much as possible`
  - `Save`
  - We can now check the agent connections logs to debug incase any issues.


## Create a new pipeline project in your Jenkins server.
  - Configure Global Build tool `Maven-3.8.4`
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
  - Under `Script Path` mention `Ch04/04_02-ssh-agent/Jenkinsfile`
  - `Save` &rarr; `Build Now`
