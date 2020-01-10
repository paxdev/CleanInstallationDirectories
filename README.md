# CleanInstallationDirectories
Task Group to clean installation directories under AzureDevops when deploying using the pattern $(InstallationRoot)\$(Release.ReleaseName)

If you deploy multiple release versions under a root directory using the pattern $(InstallationRoot)\\$(Release.ReleaseName). 
This task will query the API for Deployments on this Release in the same Release Environment.
It will find the last $(OldReleasesToKeep) Deployments that Succeeded and the Current InProgress Deployment.
It will then check all the folders under $(InstallationRoot).
If it finds at least $(OldReleasesToKeep) folders, it will keep those, plus the InProgress Release and delete the others.

Install as a Task Group in your Azure DevOps project
