# Part 2: Git Troubleshooting Practice

## Overview
This activity demonstrates common Git troubleshooting scenarios and their corresponding solutions using the Project Nova repository.

---

## 1. The "Oops, Wrong File" Problem

**Problem:** A sensitive `.env` file was accidentally staged using `git add .`.

**Solution**
```
Unstage the specific file immediately because it contains sensitive information.

Command:
git restore --staged .env
```

**Result:** The `.env` file was successfully removed from the staging area without deleting the local file.


## 2. The "Typo in the Message" Problem

**Problem:** A commit message contained a spelling error.

**Solution**
```
Correct the recent commit message without creating a new commit using --amend.

Command:
git commit --amend -m "Fixed authentication typo"
```

**Result:** The commit message was updated successfully while preserving the commit history.


## 3. The "Forgot a File" Problem

**Problem:** A required CSS file, in this example, was not included in the previous commit.

**Solution**
```
Add the missing file and include it in the previous commit.

Commands:
git add styles.css
git commit --amend --no-edit
```

**Result:** The missing file was added to the most recent commit without changing the commit message.


## 4. The "I Hate These Changes" Problem

**Problem:** Local modifications to a file were no longer needed.

**Solution**
```
Discard all uncommitted changes and restore the file to its last committed state.

Command:
git restore index.html
```

**Result:** The file was restored and all unwanted local changes were removed.


## 5. The "Wrong Branch" Problem

**Problem:** Three commits were accidentally created on the `main` branch.

**Solution**
```
Preserve the commits on a new branch and remove them from main.

Commands:
git branch new-feature
git reset HEAD~3 --hard
git checkout new-feature
```

**Result:** The commits were successfully transferred to a dedicated feature branch.


## 6. The "Detached HEAD" Problem

**Problem:** New commits were made while in a detached HEAD state.

**Solution**
```
Create a new branch to save the detached commits.

Command:
git switch -c recovery-branch
```

**Result:** The commits were preserved and attached to a new branch.


## 7. The "Undo a Pushed Mistake" Problem

**Problem:** A buggy commit was pushed to the remote repository.

**Solution**
```
Create a new commit that reverses the changes introduced by the buggy commit.

Command:
git revert <buggy-commit-hash>
```

**Result:** The unwanted changes were reversed without rewriting repository history.


## 8. The "Accidental Deletion" Problem

**Problem:** A branch containing important work was accidentally deleted.

**Solution**
```
Recover the deleted branch using its last known commit hash.

Command:
git branch <deleted-branch-name> <commit-hash>
```

**Result:** The deleted branch was successfully restored.


## 9. The "Ghost Files" Problem

**Problem:** Files were deleted outside Git and appeared as deleted in `git status`.

**Solution**
```
Stage all recorded deletions so Git can track them properly.

Command:
git add -u
```

**Result:** Git registered the deleted files and prepared them for commit.


## 10. The "Pushed to the Void" Problem

**Problem:** An unnecessary branch named `testing-junk` was pushed to GitHub.

**Solution**
```
Remove the unwanted branch from the remote repository.

Command:
git push origin --delete testing-junk
```

**Result:** The remote branch was deleted successfully.


## Conclusion

This activity helped me with troubleshooting, amending commits, restoring changes, managing, and merging branches. 
