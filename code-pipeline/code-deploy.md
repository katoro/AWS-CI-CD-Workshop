# Code Deploy 생성

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

![](<../.gitbook/assets/image (6).png>)





appspec.yml (yaml이 아니다)

```
# This is an appspec.yml template file for use with an EC2/On-Premises deployment in CodeDeploy.

version: 0.0
os: linux

files:
  - source: /
    destination: /home/ec2-user/server

permissions:
  - object: /
    pattern: "**"
    owner: ec2-user
    group: ec2-user

hooks:

  BeforeInstall:
    - location: scripts/before_install.sh
      timeout: 300
      runas: root
  
  AfterInstall:
    - location: scripts/after_install.sh
      timeout: 300
      runas: root

  ApplicationStart:
    - location: scripts/app_start.sh
      timeout: 300
      runas: root
```





before\_install

```
#!/bin/bash

# navigate to app folder
cd /app

# install node and npm
curl -sL https://rpm.nodesource.com/setup_14.x | sudo -E bash -
sudo yum -y install nodejs npm
npm install -g pm2@latest
```



after\_install

```
#!/bin/bash
cd /home/ec2-user/server
npm install
npm install --save react react-dom react-scripts react-particles-js
npm install pm2 -g

```



app\_start

```
#!/bin/bash
cd /home/ec2-user/server/src
npm start
pm2 start npm --name "app" --start
```

