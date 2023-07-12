Go to client    `/home/user/.ssh` folder
`ssh-keygen -t rsa -b 4096 -C "your_email@example.com" -f ~/.ssh/yourname_project`

`cat ~/.ssh/yourname_project.pub`
- Go to your GitHub account settings and navigate to "SSH and GPG keys."
- Click on "New SSH key" or "Add SSH key" and paste the copied key into the appropriate field.
- Save the key.

`git clone git@github.com:<username>/<repository>.git -i ~/.ssh/yourname_project`

delete pyc in git
`find . -name "*.pyc" -exec git rm -f "{}" \;`
