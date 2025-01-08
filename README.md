# Git-Practical-Exam

- Creating new Repository name Git Practical Exam 

- Initialize git-flow we use ``` git init ``` command

- Create a feature branch for project setup with the proper Zoho task ID 
  using ``` git checkout -b TE-T158_Project_Setup ```
    - create ``` index.html ``` file and add some html code as a project setup.
    - now add this file to github 
    ```
    git add index.html
    git commit -m 'add a project file name index.html'
    git push origin main
    ```

- Create new sub branch from project setup branch ``` git checkout -b TE-T158_sub_branch ```
    - Now add new 3 file and commit all.
    ```
    echo 'add data into file 1' >> file1.txt
    git add file1.txt
    git commit -m 'add new file file1.txt'

    echo 'add data into file 2' >> file2.txt
    git add file2.txti
    git commit -m 'add new file file2.txt'

    echo 'add data into file 3' >> file3.txt
    git add file3.txt
    git commit -m 'add new file file3.txt'
    ```
- for perform squash use this command ``` git rebase -i HEAD~2 ```
    - now the vim editor is open and update on it with `squash` keyword and then save it, now top two commit from HEAD is convert in onlt single commit.

- for perform reset use this command ``` git rebase --hard hash_value[69879a7] ```

- for perform rebase we make other branch and then rebase it
    ```
    git checkout -b rebase_branch

    git rebase rebase_branch
    ```

- for perform cherrypick us this command ``` git cherry-pick hash_value[69879a7] ```

[1] Create a branch from the  <br>
```
git checkout -b new_branch
```
[2] Add a commit message hook to the repo. <br> 
```
echo 'commit1' >> commitFile1.txt
git add commitFile1.txt
git commit -m 'add commit in new_branch'
```
[3] Perform multiple commits in the new branch <br>
```
modifi commitFile1.txt
git add commitFile1.txt
git commit -m 'add commit 2 in new_branch'

modifi commitFile1.txt
git add commitFile1.txt
git commit -m 'add commit 3 in new_branch'
```
[4] Create PR to develop.<br>
- To make pull request open [pull request](https://github.com/vasu-nageshri-simformsolutions/Git-Practical-Exam/pull/1) on Github and rise pr from new_branch to main. <br>

[5] PR should be small in size, It's recommended to do one commit per PR. However, based on the situation we can have multiple commits in PR. e.g. if someone is doing 10 bug fixes which are one-liner fixes in such cases instead of 10 different PRs you can do 10 commits in a single PR. 
- This pr on review <br>

[6] Create another branch from develop given your previous PR is still in review state <br> 
```
git checkout -b new_branch2
```
[7] Now commit something in your current branch and push it <br> 
```
echo 'new commit in new_branch2' >> commitFile2.txt
git add commitfile2.txt
git commit -m 'add new file in new_branch2'
git push origin new_branch2
```
[8] In the meantime, your previous PR has been merged to develop <br>
- previous pr has been review and add to main branch (merge)<br>

[9] Create a PR for the current branch given your branch should be up to date with develop branch<br>
- add pr from new_branch2 to main branch.<br>

[10] For any new build release add a version tag to that specific commit to keep track of each version.<br>
- add 3 tag v0.1, v0.2, v0.3 to diffrent commit.
```
git checkout [hash_value]
git tag tag_name
```

[11] Create 2 another branch (3rd and 4th) from develop, push read me changes to 3rd brach.<br>
```
git checkout -b new_branch3
git checkout -b new_branch4

git checkout new_branch3
git add README.md
git commit -m 'modify README.md'
```

[12] Cherry pick 3rd branch's commit to 4th branch. <br>
```
git checkout new_branch4
git cherry-pick 8d229a6[hash of 3rd branch commit]
```
[13] Change commit message in 4th branch <br>
```
git commit --amend
```
[14] add 3 commit to 4th branch and delete last commit. <br>
```
echo 'add commit 1 from new_branch4' >> commitFile3.txt
git add commitFile3.txt
git commit -m 'add commit 1 from new_branch4'

modification in commitFile3.txt
git add commitFile3.txt
git commit -m 'add commit 2 from new_branch4'

modification in commitFile3.txt
git add commitFile3.txt
git commit -m 'add commit 3 from new_branch4'
```
