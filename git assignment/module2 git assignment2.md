# module-2: git assignment -2


1. i am naming my working directory as "work"
create a new directory named "work" by using command 

mkdir work

2. change directory to work by using command 

cd work

3. for initialising git

git init

4. in "work", 
create two files by using command 

touch feature1.txt feature2.txt 

5. git config --global user.email "shiprasharmajbp@gmail.com
git config --global user.name "shipra"

6. for commiting these two files

git commit -m "committing feature1,2"

7. "as per the assignment, Create three branches develop, feature1 and feature2

git branch develop
git branch feature1
git branch feature2

8. Checkout to develop branch and create a new file develop.txt

git checkout develop
touch develop.txt 

we create a file develop.txt in the develop branch, but we do not stage or commit it yet. Instead, we use the git stash command to save these changes in a stash. 

This means that the changes made to develop.txt are not lost, but they are temporarily removed from the working directory.

9. Checkout the feature1 branch

git checkout develop
touch new.txt

stage and commit this file

git add touch new.txt
git commit -m "adding new.txt to feature1 branch"

10. git checkout to develop

To retrieve the changes we had made to the develop.txt file and apply them to our working directory in the develop branch
use

git stash pop

11. for staging the changes made to develop.txt
use

git add develop.txt

12. and for commiting the changes to develop.txt
use

git commit -m "commiting develop.txt from stash"

