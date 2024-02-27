Go to client    `/home/user/.ssh` folder
```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com" -f ~/.ssh/xxx
cat ~/.ssh/xxx.pub
```
- Go to your GitHub account settings and navigate to "SSH and `GPG` keys."
- Click on "New SSH key" or "Add SSH key" and paste the copied key into the appropriate field.
- Save the key.

if you want to save space set depth
```bash
find /home/odoo/.ssh/ -type f -name "*.pem" -exec chmod 600 {} \;
chmod 600 ~/.ssh/xxx

git clone git@github.com:<username>/<repository>.git -i ~/.ssh/xxx
git clone git@github.com:<repo_user>/<repo_name>.git -b branch --single-branch --depth 1 ////Github/repo_user/repo_name
git clone https://github.com/<repo_user>/<repo_name>.git -b branch --single-branch --depth 1 ////Github/repo_user/repo_name
git clone https://<yourname>:<yourpass>@github.com/<repo_user>/<repo_name>.git -i ~/.ssh/sshkey 

git clone https://OakarminIron:xxxxx@github.com/OakarminIron/Custom.git -b 17c
```

```bash
find . -name "*.pyc" -exec git rm -f "{}" \;
```

```bash
git add -A
git commit -m "zzz"
git fetch
```

```bash
git pull origin x
git reset --hard origin/x
``` 



To reduce file size
```bash
git fetch --depth 10 
git checkout --force FETCH_HEAD 
git gc --prune=all
```
To restore full
`git fetch --unshallow`