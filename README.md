# BASIC INSTRUCTIONS TO COMMIT AND ADD FOLDERS

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



NOTE THAT gpush is a script


#!/bin/zsh

# gpush — stage all changes, commit, and push

show_help() {
  cat << EOF
Usage: gpush "commit message"
       gpush --help

Stage all changes (git add .), commit with the given message, and push to the remote.

Examples:
  gpush "Update README with setup instructions"
  gpush "Fix typo in homepage"
  gpush "Add new contact form"

Options:
  --help     Show this help message
EOF
}

# Handle help
if [[ "$1" == "--help" || "$1" == "-h" || -z "$1" ]]; then
  show_help
  exit 0
fi

git add .
git commit -m "$1"
git push

