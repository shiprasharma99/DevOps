module-2: git assignment -5

1. mkdir folder
2. apt update
3. apt upgrade
4. cd folder
5. git init
6. git config --global user.name "shiprasharmajabalpur@gmail.com"
7. git config --global user.email "shiprasharma@gmail.com"
8. git branch
9. touch m.txt
10. git add .
11. git commit -m"adding m to master"


12. git checkout -b develop master
13. touch d.txt
14. git add .
15. git commit -m"committing d to develop"
16. ls


17. git checkout -b feature develop
18. touch f.txt
19. git add f.txt
20. git commit -m"adding f to feature"
21. ls


22. git checkout -b release develop
23. touch r.txt
24. git add r.txt
25. git commit -m"adding r to release"
26. ls


27. git checkout -b hotfix master
28. touch urgent.txt
29. git add .
30. git commit -m"adding urgent to hotfix"
31. ls


32. git checkout master
33. ls
34. git checkout develop
35. ls
36. git checkout feature
37. ls
38. git checkout release
39. ls
 
40. git checkout develop
41. git merge --no-ff feature
42. ls
 
43. git merge --no-ff release
44. ls


45. git log
46. git checkout master
47. git merge --no-ff develop
48. ls
49. git merge --no-ff hotfix
50. ls


51. history