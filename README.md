# Hello from my Mac

To commit go to your local folder and use >gpush "memo"
Memo is simply a memo about the changes you are committing


How to create a folder and connect to GitHub repo

Option A: Create the GitHub repo first, then clone it (easiest)
On GitHub, click the + button (top-right) → New repository.
Give it a name (e.g. my-new-project), leave it empty (no README), and click Create repository.
Copy the SSH URL it shows you.
In Terminal:
> ~/Desktop
> git clone git@github.com:YOUR-USERNAME/my-new-project.git
> cd my-new-projectNow 
the folder is mapped to the GitHub repo and you can start adding files and use gpush as usual.


Option B: Create the local folder first, then push it to GitHub
Create the folder and initialize it:
> cd ~/Desktop
> mkdir my-new-project
> cd my-new-project
> git init
> echo "# My New Project" > README.md
> git add .
> git commit -m "Initial commit"
On GitHub, create a new empty repository (same name is fine) and copy its SSH URL.
Connect and push:
> git remote add origin git@github.com:YOUR-USERNAME/my-new-project.git
> git branch -M main
> git push -u origin main
After that, you can use gpush normally inside the folder.
