git checkout -b develop	: new branch
git checkout -b master	: new branch

git chekcout develop/master : switch branch


----------------------Feature (creete and merge )-------------------------

git checkout -b sabafetaure1 develop


git checkout develop

git merge --no-ff sabafetaure1

#git branch -d sabafetaure1

git push origin develop

---------------------Release (creete and merge )--------------------------


git checkout -b release-1.2 develop

./bump-version.sh 1.2

git commit -a -m "Bumped version number to 1.2"


git checkout master
git merge --no-ff release-1.2

git tag -a 1.2

git checkout develop
git merge --no-ff release-1.2


# git branch -d release-1.2

------------------Hotfix (creete and merge )------------------------------

git checkout -b hotfix-1.2.1 master

./bump-version.sh 1.2.1

git commit -a -m "Bumped version number to 1.2.1"

git commit -m "Fixed severe production problem"

git checkout master
git merge --no-ff hotfix-1.2.1

git tag -a 1.2.1


git checkout develop
git merge --no-ff hotfix-1.2.1

#git branch -d hotfix-1.2.1



