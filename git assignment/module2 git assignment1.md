# module-2: git assignment -1

#### Based on what you have learnt in the class, do the following steps:
#### a. Create a new folder
#### b. Put the following files in the folder
##### ● Code.txt
##### ● Log.txt
##### ● Output.txt

#### c. Stage the Code.txt and Output.txt files
#### d. Commit them
#### e. And finally push them to GitHub 

## 1. create a new directory named "folder1" by using command 

```
mkdir folder1
```

## 2. change directory to folder1 by using command 

```
cd folder1
```

## 3. for initialising git

```
git init
```

## 4. in folder1, 
create three files by using command 

```
touch Code.txt Log.txt Output.txt
```

## 5. 
```
git config --global user.email "shipra@gmail.com
git config --global user.name "shipra"
```

## 6. "as per the assignment, we are only asked to stage two files 

```
git add Code.txt Output.txt
```

## 7. for commiting these two files

```
git commit -m "committing code and output file"
```

## 8. before adding the repository from local to remote, in github create a new repository "new-repository" and a personal token for later use

9. git remote add origin https://github.com/shiprasharma99/new-repository.git

10. git push -u origin master
username: shipra
password: paste the token here
