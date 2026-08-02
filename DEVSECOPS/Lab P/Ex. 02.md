# Ex.02: Explore Git and GitHub Commands

## Procedure

### Part A: Install Git

#### Step 1

Download Git from:

https://git-scm.com

#### Step 2

Install Git using the default settings.

#### Step 3

Verify the installation:

```bash
git --version
```

**Example Output**

```
git version 2.48.1
```

---

## Part B: Configure Git

Set your username:

```bash
git config --global user.name "Your Name"
```

Set your email:

```bash
git config --global user.email "youremail@example.com"
```

Check the configuration:

```bash
git config --list
```

---

## Part C: Create a Local Repository

Create a project folder:

```bash
mkdir DevSecOpsLab
```

Move into the folder:

```bash
cd DevSecOpsLab
```

Initialize Git:

```bash
git init
```

**Expected Output**

```
Initialized empty Git repository
```

---

## Part D: Create a File

Create a file:

```
README.md
```

Add the following content:

```
# DevSecOps Laboratory
```

Check the repository status:

```bash
git status
```

---

## Part E: Stage the File

Stage the file:

```bash
git add README.md
```

Or stage all files:

```bash
git add .
```

Check the repository status:

```bash
git status
```

---

## Part F: Commit Changes

Commit the changes:

```bash
git commit -m "Initial Commit"
```

View the commit history:

```bash
git log
```

Push the changes to the remote repository:

```bash
git push
```
