# Creating new version

# update from remote
git checkout master
git pull origin master

# update repo from upstream
git pull upstream

# update list of tags
git fetch --tags

# change to the latest official version branch
git checkout vX.X.X

# cherry-pick our patch without committing and check if no conflict
git cherry-pick -n cpt-patch

# build patched version
grunt

# add and commit the result
git add -f build/angular.js build/angular.min.js
git commit

# after successful build set a new tag
git tag -a -m "cpt patch" vX.X.X-cpt

# push remote
git push
git push --tags

