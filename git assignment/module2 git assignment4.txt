module-2: git assignment -4

Put master.txt on master branch, stage and commit
● Create 3 branches: public1, public2 and private
● Put public1.txt on public 1 branch, stage and commit
● Merge public 1 on master branch
● Merge public 2 on master branch
● Edit master.txt on private branch, stage and commit
● Now update branch public 1 and public 2 with new master code in private
● Also update new master code on master
● Finally update all the code on the private branch

1. i am naming my git working directory as "git-repository"
create a new directory named "git-repository" by using command 

mkdir git-repository

2. change directory to work by using command 

cd git-repository

3. Initialize a new Git repository with 

git init

4. Create the master branch
git branch master
touch master.txt
git add master.txt
git commit -m"commiting master.txt to master branch"

5. Create three branch 
public1
public2
private

git branch public1
git branch public2
git branch private

6. Put public1.txt on public 1 branch, stage and commit 

git checkout public1
touch public1.txt
git add public1.txt
git commit -m "Adding public1 to public1 branch"

8. Merge public1 on master branch 

git checkout master
git merge --no-ff public1

9. Merge public2 on master branch

git merge --no-ff public2

10. Checkout to private branch

git checkout private


11. Edit master.txt on private branch, stage and commit 

ls
vi master.txt
git add master.txt
git commit -m "Edited master.txt file on private branch"

12. Update the public1 and public2 branches with the new master

git checkout public1
git merge master
git checkout public2
git merge master

13. Now update branch public 1 and public 2 with new master code in private 

git checkout master
git merge private

Finally, update all the code on the private branch 

git checkout private
git merge master
git merge public1
git merge public2


