#  GitLab to GitHub Repository Mirroring

This project demonstrates how to mirror a GitLab repository to GitHub, ensuring that both repositories remain automatically synchronized.

##  Overview

Repository mirroring allows you to keep two repositories synchronized — for example, pushing code from GitLab to GitHub automatically whenever changes are made.

###  Why Use Repository Mirroring?

- Backup your GitLab repository to GitHub
- Collaborate across different platforms
- Maintain public and private copies of the same project
- Ensure redundancy and availability

#  Step-by-Step Implementation

##  Step 1: Create Repository in GitHub

Create a new repository in GitHub and initialize it with a README file.

![Create repo on GitHub](images/Create%20repo%20on%20GitHub.png)


##  Step 2: Create Personal Access Token (Classic)

Go to:

GitHub → Settings → Developer Settings → Personal Access Tokens → Tokens (classic) → Generate New Token

Grant required permissions (repo access recommended).

![Create access token on GitHub-1](images/Create%20access%20token%20on%20GitHub-1.png)

![Create access token on GitHub-2](images/Create%20access%20token%20on%20GitHub-2.png)

After generating the token, copy it immediately. You will use it as a password in GitLab mirror configuration.


##  Step 3: Create Blank Project in GitLab

1. Go to GitLab
2. Click **New Project**
3. Choose **Blank Project**
4. Initialize repository with README


![Create Blank Project on GitLab](images/Create%20Blank%20Project%20on%20GitLab.png)


##  Step 4: Add New Mirror Repository in GitLab

Go to:

Project → Settings → Repository → Mirroring Repositories

Click **Mirror Repository**

Use this format for Git repository URL:
https://<GITHUB_USERNAME>@github.com/<GITHUB_USERNAME>/<GITHUB_REPO>.git

![Add a new mirror repo on GitLab](images/Add%20a%20new%20mirror%20repo%20on%20GitLab.png)


##  Step 5: Use GitHub Token as Password

When prompted for password:

- Username → Your GitHub username
- Password → Paste GitHub Personal Access Token

![use password(token) in mirror repo on gitlab](images/use%20password(token)%20in%20mirror%20repo%20on%20gitlab.png)

Click **Mirror repository** to complete setup.

## 🔹 Step 6: Clone GitLab Repository & Push Code

Clone repository:

```bash
git clone https://gitlab.com/<GITLAB_USERNAME>/<GITLAB_REPO>.git
cd <REPO_NAME>
```

Create and push a file:
```bash
cat index.html
```

Add content: 
```bash
<h1>This is my mirror repo project</h1>
```

Commit and push: 
```bash
git add index.html
git commit -m "index.html file added"
git push -u origin main
```

##  Output Verification

1. File in GitLab Repository

![file in your GitLab repository](images/file%20in%20your%20GitLab%20repository.png)

2. Add Any One File and Push on GitLab

![add any one file and push on gitlab](images/add%20any%20one%20file%20and%20push%20on%20gitlab.png)

3. Done Successfully (Mirrored to GitHub)

![done successfully](images/done%20successfully.png)

Now the same file will automatically appear in your GitHub repository because of push mirroring.

##  Conclusion
By configuring GitLab push mirroring:
* Your GitLab repository automatically syncs with GitHub
* Every commit pushed to GitLab is reflected in GitHub
* Your project stays backed up and synchronized
* Collaboration across platforms becomes easier
* GitLab’s push mirror feature makes the workflow automated, secure, and efficient.