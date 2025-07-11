# 04_02 SSH agent
## Connect to a node via SSH.
## Requirments:
  - Serrver that is accessible from jenkins.
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

## Build a Project using SSH agent
  - Configure Global Build tool `Maven-3.8.4`
  - Use this [`Jenkinsfile`](./Jenkinsfile)
