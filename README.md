### 1. **Clone or Initialize the Repository**
If you already have a local Git repository:
- Skip to Step 2.
  
If not:
```bash
git init
git add .
git commit -m "Initial commit"
```

### 2. **Add Azure Repos as a Remote**
If your repository is hosted in Azure DevOps:
1. Go to Azure DevOps and create a new repository if you haven't already.
2. Copy the repository's HTTPS or SSH URL.
3. Add Azure Repos as a remote to your local repository:
   ```bash
   git remote add azure <Azure_Repo_URL>
   ```

### 3. **Add GitHub as a Remote**
1. Go to GitHub and create a new repository if you haven't already.
2. Copy the repository's HTTPS or SSH URL.
3. Add GitHub as another remote to your local repository:
   ```bash
   git remote add github <GitHub_Repo_URL>
   ```

### 4. **Verify the Remote URLs**
To confirm that both remotes are set up correctly:
```bash
git remote -v
```
You should see both `azure` and `github` listed.

### 5. **Push Changes to Both Repositories**
Whenever you make changes and commit them locally, you can push to both repositories:
```bash
git push azure main
git push github main
```
Replace `main` with the branch name you're working on if it's different.

### 6. **Optional: Set Up a Script for Dual Push**
To avoid manually pushing to both repositories every time, you can create a Git alias or a simple script to push changes to both remotes with one command.

Example script (`push_to_both.sh`):
```bash
#!/bin/bash
git push azure main
git push github main
```
Make it executable:
```bash
chmod +x push_to_both.sh
```

Then, use it after committing changes:
```bash
./push_to_both.sh
```
