**EXTREMELY IMPORTANT WARNINGS:**

1. **`git reset --hard` is Destructive Locally:** This command _permanently throws away_ commits from your local history. It also **discards any uncommitted changes** in your working directory and staging area. Be absolutely sure you want to lose that work. THERE IS NO EASY UNDO LOCALLY AFTER THIS (though `git reflog` might offer a lifeline _if used immediately_ and only affects your local repo).
2. **Force Pushing Rewrites Shared History:** Pushing these changes to GitHub requires a force push. If anyone else has pulled the branch with the commits you are about to remove, force pushing **WILL CAUSE MAJOR PROBLEMS** for them. Coordinate with collaborators _before_ doing this, or only do it on branches you exclusively control.
3. **Backup:** Consider backing up your branch or repository before starting, just in case.

Here is the step-by-step process:

**Part 1: Removing Commits Locally**

1. **Identify the Target Commit:**
    
    - Use `git log --oneline --graph` (or just `git log`) to view your commit history.
    - Find the **last commit you want to keep**. This is the commit your branch history will end at after the reset. All commits _after_ this one will be discarded.
    - Copy the full SHA-1 hash (the long string) of this commit. Let's call it `<hash-of-last-commit-to-keep>`.
2. **Checkout the Branch:**
    
    - Make sure you are on the branch you want to modify:
        
        Bash
        
        ```
        git checkout your-branch-name
        ```
        
3. **Perform the Reset:**
    
    - Execute the `git reset --hard` command, using the hash you identified:
        
        Bash
        
        ```
        git reset --hard <hash-of-last-commit-to-keep>
        ```
        
    - Git will confirm that `HEAD` is now at the specified commit.
4. **Verify Locally:**
    
    - Run `git log` again. You should see that your branch history now stops at `<hash-of-last-commit-to-keep>`. The more recent commits are gone from your local history.

**Part 2: Making Sure It's Removed from GitHub**

Now that your local history is correct, you need to update the remote repository on GitHub.

5. **Force Push to GitHub:**
    
    - Since your local history has been rewritten and diverges from what's currently on GitHub, you _must_ use a force push.
    - **`--force-with-lease` is generally safer** as it helps prevent accidentally overwriting work someone else might have pushed since you last pulled.
    - Execute the command:
        
        Bash
        
        ```
        # Preferred, safer option:
        git push --force-with-lease origin your-branch-name
        
        # Alternative (use with extreme caution, especially if shared):
        git push --force origin your-branch-name
        ```
        
    - Git will push your rewritten local history to GitHub, replacing the previous history on the remote branch.
6. **Verify on GitHub:**
    
    - Go to your repository on the GitHub website.
    - Navigate to the branch you just pushed (`your-branch-name`).
    - Check the commit history for that branch online. It should now match your local history, ending at `<hash-of-last-commit-to-keep>`, and the newer commits should be gone.

By following these steps, you first remove the commits after a certain point in your local repository using `git reset --hard` and then overwrite the history on GitHub using a force push, ensuring the removal is reflected there as well. Remember to be cautious, especially with the `reset --hard` and force push commands.