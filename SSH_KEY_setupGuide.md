# SSH Key Setup for GitHub

| **Step** | **Command / Action**                                                                             | **Description**                           |
| -------- | ------------------------------------------------------------------------------------------------ | ----------------------------------------- |
| 1️⃣      | `ssh-keygen -t ed25519 -C "your_email@example.com"`                                              | Generate a new SSH key                    |
|          | At prompt: `/home/yourname/.ssh/github_ed25519`                                                  | Save key to custom path (avoid overwrite) |
|          | \[Press Enter]                                                                                   | Optional: Add passphrase                  |
| 2️⃣      | `eval "$(ssh-agent -s)"`                                                                         | Start the SSH agent                       |
| 3️⃣      | `ssh-add ~/.ssh/github_ed25519`                                                                  | Add your new key to the agent             |
| 4️⃣      | `cat ~/.ssh/github_ed25519.pub`                                                                  | Copy your **public key**                  |
| 5️⃣      | GitHub → [https://github.com/settings/keys](https://github.com/settings/keys)                    | Add a **new SSH key**                     |
|          | Title: `10nac GitHub SSH Key`                                                                     | A name for the key                        |
|          | Paste your copied key                                                                            | In the key field                          |
|          | Click `Add SSH Key`                                                                              | Save it to GitHub                         |
| 6️⃣      | `nano ~/.ssh/config`                                                                             | Create or edit SSH config file            |
|          | Add:                                                                                             |                                           |
|          | `Host github.com`<br>`HostName github.com`<br>`User git`<br>`IdentityFile ~/.ssh/github_ed25519` | Configure GitHub to use your new key      |
| 7️⃣      | `git remote set-url origin git@github.com:YourUsername/YourRepo.git`                             | Set repo to use SSH URL                   |
| 8️⃣      | `ssh -T git@github.com`                                                                          | Test SSH connection                       |
| 9️⃣      | `git push -u origin main`                                                                        | Push your code to GitHub via SSH          |
