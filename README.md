# Git Assignment 2 Workflow

## Step 1: Initialize the Repository
```bash
mkdir git-assignment-2
cd git-assignment-2
git init
echo hello > README.md
git add README.md
git commit -m "Added README.md"
git remote add origin https://github.com/prithu-anan/ic-devops-batch3-git-assignment-2.git
git push -u origin main
```

## Step 2: Create and Work on Feature Branches

### Create `feature-1` Branch
```bash
git checkout -b feature-1
echo world > file1.txt
git add file1.txt
git commit -m "Added file1.txt"
```

### Create `feature-2` Branch
```bash
git checkout main
git checkout -b feature-2
echo interactive-cares > file2.txt
git add file2.txt
git commit -m "Added file2.txt"
```

### Push Feature Branches to Remote
```bash
git push -u origin feature-1
git push -u origin feature-2
```

## Step 3: Rebase and Update Feature Branches

### Rebase `feature-1` onto `main`
```bash
git checkout feature-1
git fetch origin main
git rebase main
git push --force-with-lease
```

### Rebase `feature-2` onto `main`
```bash
git checkout feature-2
git fetch origin main
git rebase main
git push --force-with-lease
```

## Step 4: Clean Up Merged Branches

### Delete Local and Remote Feature Branches
```bash
git checkout main
git branch -d feature-1
git branch -d feature-2
git push origin --delete feature-1
git push origin --delete feature-2
```

## Step 5: Finalize and Verify

### Pull Changes and View Commit History
```bash
git pull
git log --oneline
```

### Modify README and Push Changes
```bash
git add .
git commit -m "Modified the README.md file"
git push -u origin main
```
