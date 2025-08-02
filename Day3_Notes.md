## 07/31/25 Guacamole Exercises

For my own benefit, I’m trying to summarize the major commands / steps we covered in the first half of Thursdays’s lesson where we modified the Guacamole recipe.  I’d appreciate my classmates and course assistants telling me if these instructions seem correct:

#### A. Cloning the DSI Guac Recipe onto our computer

##### 1. Clone DSI Guac Repository

``` git clone https://github.com/dtxe/dsi_guacamole ```

##### 2. Examine for history of any changes

``` git log ```

##### 3. During this step, it was noticed that two commits were downloaded.  They have separate commit codes. To check on the markdown file, open the markdown file in VSCode.

```  code guacamole.md ``` 

### B. Restoring a previous non-erroneous version of the guacamole recipe

##### 4. After noticing an error with the most recent commit for guacamole recipe, try to revert to a previous commit.  First make a new branch that connect to a previous commit.

``` git switch -c fix-avocados e4912279bfddcc05c9c91924cd40efcf04f2f1c3 ```

##### 5. Check on the markdown file again, open the markdown file in VSCode.

``` code guacamole.md ```

  The guacamole recipe now seems correct.

 ### C. Now, we want to put this “correct” recipe on GitHub.  Make a fresh repository on your GitHub.

#### 6. Fork the dsi_guacamole repository,  or
#### 7. Create a new repository using the drop-down menu on GitHub (instructor did this, and named the repository “my_guac_recipe”).

(In theory, we should also be able to create a new repository in the command line using git init, but I’m not sure how to do this quite yet…).

### D. Push the “correct” guacamole recipe to a repository on GitHub for which we have access.  

#### 8. Began by renaming the remote “origin” to “upstream”.  Now the remote “upstream” points to the DSI_course repository, which we are unable to access for push and pull.

``` git remote rename origin upstream ```

#### 9. Now, define a remote named origin that points to the individual repository we just created.

``` git remote add origin https://github.com/GitHubUserName/my_guac_recipe ```

The URL will be the address of your individual repository.  The command adds / redefines “origin” as the remote that points to our individual repository.

#### 10. Push changes from your computer onto your personal GitHub repository.

``` git push -u origin fix-avocados ```

Origin is the “remote” that points to our personal directory and “fix-avocados” is the branch we’ve created in our directory for this guacamole exercise.  

### E. Now we want to remove peppers from the guacamole recipe

#### 11. Open the guacamole.md recipe in some kind of text editor.  Instructor prefers VSCode.  
#### 12. Manually delete the jalapeños from the recipe and save the file.
#### 13. Update the changes in the online repository:

```
git add guacamole.md
git commit -m “commit message of choice”
git push
```

### F. Integrate other users’ changes to the Guacamole recipe.

#### 14. Note that there is another branch on https://github.com/dtxe/dsi_guacamole called “big-batch”.  This branch contains a version of the guacamole recipe resized for 10 people.
#### 15. Download changes using a pull request

 ``` git pull upstream big-batch ```

For Mac users: 

``` git pull —no-rebase upstream big-batch ```

#### 16. Use VSCode to examine guacamole.md

``` Code guacamole.md ```

Will get error messages indicating that there are two versions of guacamole.md. VSCode will open with one version highlighted in green (current code) and the other version highlighted in blue (incoming change).  

#### 17. Examine the two versions of the recipe and decide what we want.  In this case, we want to scale up the recipe but also remove the jalapeños.
#### 18. Click the option to “accept incoming change” to the accept the scaled up recipe.
#### 19. Manually delete the jalapeños.
#### 20. Save the file.
#### 21. Update the changes in the online repository:

```
 git add guacamole.md
 git commit -m “commit message of choice”
 git push
```
