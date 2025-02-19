IMPORTANT NOTE FROM YOUR BOY'S SIDE:

Basically I learnt all these commands below and practiced it using this repo only. I first completed all that and then deleted 
the entire history of this repo (as pushing them to my github would unnecessarily increase my commit count & clutter 
my profile) and then extracted all those commands I learnt while doing these intermediate git lessons from The Odin Project 
and gave it to ChatGpt for properly modifying it and making a git ready .md file out of that with all those bullets,headings, 
spacings,etc that provides a proper structure for the reader (as I don't know how to do that manually using *, #, - and all that).
It was a hard time there too with juggling back and forth with Gpt(4o) to make it understand the purpose and format the file accordingly. 

But yaa I guess it was all worth it with the kind of final result i got. 
I solely made this file for documenting my learning curve while not unnecessarily cluttering my Git profile. Hopefully, the 
outcome below gives you a good overview of what your boy learnt during this duration and what's the purpose of this file. 

Thank You!🖤❤️🖤



# Git Commands

## 1. Modifying Commits

### Changing the Last Commit
- **`git commit --amend`**  
  Modify the most recent commit (e.g., change the commit message or add more changes).

### Changing Multiple Commits
- **`git rebase -i HEAD~N`**  
  Interactive rebase to modify the last N commits.
- **`git commit --amend`**  
  Modify a specific commit during the rebase.
- **`git rebase --continue`**  
  Continue the rebase process after making changes.

## 2. Squashing Commits
- Example:
  ```sh
  pick e30ff48 Create first file
  squash 92aa6f3 Create second file
  ```
  - Use `pick` for the first commit and `squash` for subsequent ones.
  - Edit the commit message as needed before saving.

## 3. Splitting a Commit
- **`git reset HEAD~`**  
  Moves changes from the last commit back to the staging area.
- Modify files and create new commits as needed.
- Alternative methods:
  - **`git reset --soft HEAD~1`** (keeps changes staged)
  - **`git reset --hard HEAD~1`** (discards changes completely)

## 4. Force Pushing and Undoing Commits

### Force Pushing
- **`git push --force`**  
  Overwrites the remote repository with local history.
  - **Caution:** This can delete commits made by collaborators.
  - **Safer Alternative:** Use **`git push --force-with-lease`** to check if the remote branch has been updated before forcing.

### Undoing a Commit Safely
- **`git revert HEAD`**  
  Creates a new commit that undoes changes from the latest commit.
  - **Best practice:** Use this instead of `git push --force` when working with a team.

## 5. Best Practices for Rewriting History
- Avoid rewriting history on shared branches.
- Use force push (`-f`) only when absolutely necessary.
- Do not amend, rebase, or reset commits that have been pushed to remote repositories unless it is safe to do so.
- Communicate with your team before rewriting history.

## 6. Open Source Contributions

### Initial Setup
1. **Fork a Repository**: Use the “Fork” button on GitHub.
2. **Clone Your Fork**:
   ```sh
   git clone git@github.com:your_user_name_here/repository.git
   ```
3. **Add Upstream Remote**:
   ```sh
   git remote add upstream git@github.com:original_owner/repository.git
   ```

### Ongoing Workflow
1. **Create a Feature Branch**:
   ```sh
   git checkout -b your_feature_name
   ```
2. **Fetch Latest Updates**:
   ```sh
   git fetch upstream
   ```
3. **Merge Upstream Changes into Main**:
   ```sh
   git checkout main
   git merge upstream/main
   ```
4. **Merge Main into Feature Branch**:
   ```sh
   git checkout your_feature_name
   git merge main
   ```
5. **Resolve Merge Conflicts if Any** (manually resolve conflicts and commit changes).

### Sending Your Pull Request
1. **Push Feature Branch to Origin**:
   ```sh
   git push origin your_feature_name
   ```
2. **Create a Pull Request on GitHub** (via GitHub interface).

## 7. Additional Git Commands

### Checking and Managing Branches
- **Check Remote Repositories**:
  ```sh
  git remote -v
  ```
- **Check Current Branch**:
  ```sh
  git branch
  ```
- **Switch Branch**:
  ```sh
  git checkout branch_name
  ```
- **Delete a Branch**:
  ```sh
  git branch -d branch_name
  ```

### Staging, Committing, and Pushing Changes
- **Stage and Commit Changes**:
  ```sh
  git add .
  git commit -m "Your commit message"
  ```
- **Push Changes to Remote**:
  ```sh
  git push origin branch_name
  ```
- **Pull Latest Changes**:
  ```sh
  git pull origin branch_name
  ```