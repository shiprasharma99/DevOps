### You work as a Devops Architect in Zendriix Softwares. The company has been struggling to manage their product releases. The releases should happen on 25th of every month. Suggest a Git Workflow Architecture for this requirement. Simulate this workflow, by creating a pseudo code files and branches, and upload the same to your GitHub Account.

# 1. Initialise git by git init

# 2. Created three branch
1. master
2. develop 
3. release

```
git checkout -b develop master 
git checkout -b release develop
```

# 3. Added main to master
added patch1 and hotfix to develop

# 4. Git remote add origin (my git url)
```
git push origin master
```

# 5. added git-release.sh

```
#!/bin/bash

#cd /path/to/your/local/repo
```

Update the master branch
```
git checkout master
git pull
```

Create a release branch
```
git checkout -b release-$(date +%Y%m%d%H%M)
```
Push the release branch to the remote repository
```
git push origin release-$(date +%Y%m%d%H%M)
```

# 6. executred it by using this command- 

```
./git-release.sh
```
