Go to client    `/home/user/.ssh` folder
```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com" -f ~/.ssh/xxx
cat ~/.ssh/xxx.pub
```
- Go to your GitHub account settings and navigate to "SSH and `GPG` keys."
- Click on "New SSH key" or "Add SSH key" and paste the copied key into the appropriate field.
- Save the key.

```
find /home/odoo/.ssh/ -type f -name "*.pem" -exec chmod 600 {} \;
chmod 600 ~/.ssh/xxx

git clone git@github.com:<username>/<repository>.git -i ~/.ssh/xxx
```

```bash
find . -name "*.pyc" -exec git rm -f "{}" \;
```

```
git add -A
git commit -m "zzz"
git fetch
```

```
git pull origin x
git reset --hard origin/x
``` 