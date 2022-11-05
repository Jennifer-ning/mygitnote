#Command line and git commands

##Terminal command lines

Point working directory:       pwd
Create a new directory:       mkdir -p file_path
Go to a folder:                      cd folder_name
Come back to last directory:      cd ..
Copy a file:                              cp -R old_directory new_directory( or use . represent the current location)
Remove a file:                       rm file_name
                                                   rm -rf folder_name/file_name (remove recursively and by force)
Rename a file:                       mv old_file_name new_file_name


==============================================================================
##Git command lines

git config —global —list: list all global configuration in history.
git init repo_name: create a git repository
git status: check what is going on in the git repository
git add file_name: move the file from the working directory into the staging area.
git add . : add multiple files together at one action
git add -u: update files to in the staging area
git add -A: cover all possible modifications and make updates accordingly in Git index
git commit -m “ some your commit message of the file”: move file from staging area to repository.
git commit -am file_name: add the modification to staging area and then commit those changes.
git commit --amend: It lets you combine staged changes with the previous commit instead of creating an entirely new commit. 
git log: show all commits that are part of this current repository.
git log —graph: graph denoting the branching hierarchy.
git log —all: give all the branches in the repository.
git reflog: show all different action we have taken not only commit ids.
git show commit_id/tag_name: show the commit/tag with the commit_id /tag_name and a diff containing all the changes.
git ls-files: tell what git is tracking
git checkout — file_name: revert back to the last known good state of that file which is back in git repository.
git checkout commit_id: revert back to the commit location and open a branch named the commit_id to edit.
git checkout branch_name: revert back to a target branch
git checkout -b branch_name (remote_point): create to a new branch, the remote_point is used when there is more than one remote connections and it means the location in remote repository such as origin/branch1
git mv old_file_name new file_name: rename file name
git rm file_name: remove a file
git diff commit_id1 commit_id2: get the difference between two commits
git difftool commit_id1 commit_id2: launch the configured diff tool
git branch: to show the branches of the current repository
git branch -a: to show all the branches
git branch -m branch_name: move to or rename the current branch to the name we specify
git branch -d branch_name: delete the branch
git merge branch_name: merge the branch into the main branch
cat file_name: output the entire contents of a file
git mergetool: a merge tool configured with git
git tag tag_name branch_name: give a light-weight tag on the specific branch
git tag (—list): list all tags
git tag -d tag_name: delete the tag
git tag -a tag_name -m “some_description” commit_id: add an annotated tag with tag_name and description at the specific commit location.
git tag -f existing_tag commit_id: update the existing tag to the new local commit_id.
git push -force origin tag_name: force the remote repository to update the modified existing local tag. Rarely use and be careful.
git stash: save the current head at the current branch
git stash pop:  apply the last stash and put those changes back in the target file, then drop the stash
git reset commit_id /HEAD~ —soft/—mixed/hard: pass to the commit id I want to reset to. —soft save the following changes into staging area, —mixed save them before staging step, —hard directly wipe them out.
git push origin HEAD --force: If you pushed a head commit, and delete it in the local, you will need to do a force push to get rid of it
git remote -v, git remote show origin: show the remote connection repository
git remote add origin https://github.com/Jennifer-ning/demo.git: create connection, add subcommand show the name of the remote reference we want to create such as ‘origin’, URL is the remote repository with personal access token.
git remote add new_remote_repository_name parent_URL: add another remote repository such as the parent repository of fork.
git remote set-url origin git@github.com:Jennifer-ning/demo.git: create connection, update remote repository name, add subcommand show the name of the remote reference with SSH key.
git push -u origin main —tag: set up a tracking branch relationship between the main branch on the local repository and the main branch on the remote repository. ‘origin” is the remote repository name, ‘main’ is the local one. -u means the two branches’ relationship is tracked to keep sync with each other. —tag is to send all the tags to GitHub. 
git push origin tag_name: push the specific tag to the remote.
git push origin :branch_name/tag_name: tell GitHub to delete whatever the name of the branch/tag after the colon(:).
git clone github_URL your_local_folder_name:  point to an existing remote repo and make a clone or copy of that repo at in a new directory, at another location with your preferred folder name.
git fetch (—all): go out to the remote repository, and update and show its references to the local repository. —all means pull all remote references from all remote repositories
git fetch -p:  go to remote repository and look for any dead branches and remove those references.
git pull: after git fetch, merge changes between local and remote current branches when changes are make on both sides or by multiple people, and then git push.
git pull —all: update all changes of all remote branches into local repository.
git pull —rebase: to cause a rebase to first rewind the local branch and make it follow the changes from Github.




touch file_name: add a new file.
mate file_name.extension:  create a new mate file
mate .gitignore: exclude file and folders not to track

##SSH key generation:
Step 1: at the local directory (cd ~),  mkdir .ssh (create ssh directory), cd .ssh (go to the ssh directory).
Step 2: ssh-keygen -t rsa -C “ningzhang16868@gmail.com” (generate public and personal ssh keys). Press Enter for no passphrase. The key is generated. 
Step 3: ls -al (show all ssh files). mate id_rsa.pub (open file with .pub for public ssh key.)
Step 4: copy the contents opened in step 3. Go to GitHub to paste it at the ‘SSH and GPG keys’ in ’Settings’.
Step 5: ssh -T git@githib.com (got to terminal and to confirm the machine is able to communicate with GitHub)
