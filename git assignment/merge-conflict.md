# CASE STUDY- RESOLVING MERGE CONFLICTS

#### Problem Statement:

#### You work for Zendrix Software & Co. You have been assigned the task of updating the Master branch of their Git repository with all the features from the feature branches.Following is the GitHub account, https://github.com/devops-intellipaat/merge-conflict.git

#### Consider,
#### 1. Feature1 branch to be a public branch
#### 2. Feature2 branch to be a private branch
#### The company relies on a monolithic architecture, and for now all the code resides in one file “main.c”. The respective features have been added in the feature branches for main.c. Meanwhile, a security patch was made to the master branch, and now feature1 and feature2 branches are behind from master by 1 commit. 

#### Following tasks have to be done:
#### 1. Update Feature1 and Feature2 branch with the Security Patch
#### 2. Apply changes of Feature1 and Feature2 branch on master
#### 3. Finally push all the branches to GitHub
#### For Solving this, please fork the repository to your Github account and then work. As a solution, please submit your GitHub’s repository link.



### I have forked this git url- https://github.com/devops-intellipaat/merge-conflict.git

### I have cloned it to my local repository by using git clone (my-git-url)

### 
```
git pull origin master
```

### Since feature1 and feature2 doesn't exist so i created both branches

```
git checkout -b feature1 master(containing original main.c)

git checkout -b feature2 master(containing original main.c)
```

### A security patch was made to the master branch,

```
git checkout master
```

### to add a security patch in the main.c file of the master branch

```
added //security patch 1 
```
to main.c in master

```
$ cat main.c
pseudo code
{
Initial Function()
{
  //Sample Code
}

Initial Security()
{
 //Sample Code
}
pseudo code



}
//security patch 1 - master
```
```
git add main.c

git commit -m "master securitypatch1"

```
  
### feature1 and feature2 branches are behind from master by 1 commit

```
git checkout feature1

```
### Merge the changes from the master branch into the feature1 branch
```
git merge master

git checkout feature2

git merge master

git push origin feature1

git push origin feature2
```
https://github.com/shiprasharma99/merge-conflict