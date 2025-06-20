# Make sure to download this markdown file for later use..

# git process

| Step | Command / Action                                   | Description                                                       |
| ---- | -------------------------------------------------- | ----------------------------------------------------------------- |
| 1️⃣  | `git init`                                         | Initialized Git in your local project folder.                     |
| 2️⃣  | `git remote add origin <repo-url>`                 | Connected your local folder to the GitHub repo.                   |
| 3️⃣  | `git add .`                                        | Staged all your files to be committed.                            |
| 4️⃣  | `git commit -m "message"`                          | Committed the files to local Git history.                         |
| 5️⃣  | `git branch -M main`                               | Renamed branch to `main` (modern Git default).                    |
| 6️⃣  | `git pull origin main --allow-unrelated-histories` | Pulled GitHub’s README/init files into your project using rebase. |
| 7️⃣  | `git config pull.rebase true`                      | Told Git to rebase when pulling remote changes.                   |
| 8️⃣  | `git push -u origin main --force`                  | Force pushed your changes to update the GitHub repo.              |


# Mistake's I made while I Learn Pushing a folder in a github repository.

Mistake	🛠️ Fix

1-Tried to use GitHub password for push	Used Personal Access Token (PAT) instead. Password authentication is deprecated.

2-Error: Updates were rejected because the remote contains work...	Pulled remote changes using --allow-unrelated-histories.

3-Git failed to pull due to rebase settings	Solved with git config pull.rebase true (you chose rebase strategy).

4-Confused by not seeing files on GitHub after push	Found you were in the correct folder, but hadn’t added/committed the files yet. Fixed by doing git add . and git push.

Bonus Tips

| Task                                          | Command                                       |
| --------------------------------------------- | --------------------------------------------- |
| See current branch                            | `git branch`                                  |
| Check remote URLs                             | `git remote -v`                               |
| View commit log                               | `git log --oneline`                           |
| Set credential helper (no more token prompts) | `git config --global credential.helper store` |
| View hidden files (e.g., `.git`)              | `ls -a`                                       |

