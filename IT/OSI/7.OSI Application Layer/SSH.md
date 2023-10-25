`find /path/to/pem/ -type f -name "*.pem" -exec chmod 600 {} \;`

Generate SSH Key Pair: On your local laptop generate an SSH key pair (if you haven't already). Open a terminal (command prompt) and use the following command:
```local
ssh-keygen -t rsa -b 4096 -f ~/.ssh/dev
```

Copy the Public Key to the Remote Server: Now, you need to copy the public key (`dev.pub`) to the remote server. Use the following command in your terminal:

```local
ssh-copy-id -i ~/.ssh/dev.pub dev@9.9.9.9
```

or cat in your laptop 
`cat ~/.ssh/dev.pub`  and copied in remote
```remote
mkdir -p ~/.ssh 
touch ~/.ssh/authorized_keys
nano ~/.ssh/authorized_keys
chmod 700 ~/.ssh 
chmod 600 ~/.ssh/authorized_keys
```

