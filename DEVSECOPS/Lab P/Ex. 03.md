# Ex.03: Practice Source Code Management on GitHub (Experiment 01)

## Procedure

### Part A: Create a GitHub Repository

1. Log in to your GitHub account.
2. Click **New Repository**.
3. Enter the repository name:
   ```
   test
   ```
4. Choose the repository visibility (**Public** or **Private**).
5. Add a **README.md** file.
6. Click **Create Repository**.

---

### Part B: Create a GitHub Account

If you do not already have a GitHub account, create one by visiting the GitHub website and completing the registration process.

---

### Part C: Create a New Repository on GitHub

1. Log in to your GitHub account.
2. Click the **"+"** icon in the top-right corner and select **New repository**.
3. Enter the repository name, description, and other required details.
4. Select the repository visibility (**Public** or **Private**).
5. Optionally, add a license and a **README.md** file.
6. Click **Create repository**.

---

### Part D: Clone the Repository to Your Local Machine

On the repository page, click the **Code** button and copy the repository URL.

Open **Terminal** or **Command Prompt**.

Navigate to the desired directory and clone the repository:

```bash
git clone <repository-url>
```

---

### Part E: Move to the Repository Directory

Navigate to the cloned repository:

```bash
cd <repository-name>
```

---

### Part F: Add the Source Code

Create a new file in the repository and add the source code written in **Exercise 01**.

---

### Part G: Stage the Changes

Stage the file for commit:

```bash
git add <file-name>
```

---

### Part H: Commit the Changes

Commit the staged changes with a meaningful message:

```bash
git commit -m "Added source code for a simple user registration form"
```

---

### Part I: Push the Changes to GitHub

Push the committed changes to the remote repository:

```bash
git push origin master
```

---

### Part J: Verify on GitHub

Open your GitHub repository in a web browser and verify that the uploaded files and commit are successfully reflected in the repository.
