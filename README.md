# This Readme is a workflow of the DevOps Presentation

## Ansible Image with local Repo
This will launch a SNOPS container variant with Ansible installed and a local Repo Mapped
SNOPS:https://github.com/f5devcentral/f5-super-netops-container
Ansible MVP:https://github.com/jmcalalang/ansible_f5

```docker run -p 8080:80 -p 2222:22 --rm -it -v "/Volumes/JC Drive/GitHub Repository/ansible_f5/misc/user_repos.json:/tmp/user_repos.json" -e SNOPS_GH_BRANCH=develop f5devcentral/f5-super-netops-container:develop-ansible```

## Jenkins Server
Login to Jenkins Server and Start

```java -jar jenkins.war```

## f5_chatbot
Chatbot is a ChatOps solution working with F5 iWorkflow, Hubot and Slack
Chatbot:https://github.com/npearce/f5_chatbot
```docker run -t --rm -e HUBOT_SLACK_TOKEN={{your magnificent token}} --name f5_chatbot_beta npearce/f5_chatbot:release_v0.1-beta2 ./bin/hubot --adapter slack```

Once you are talking with @f5_bot

``install service templates``
``install iapps``

This will deploy the Http-LB service through @f5_bot and iWorkflow

```deploy service %7B%0D%0A++++%22name%22%3A+%22jon-word-press%22%2C%0D%0A++++%22tenantTemplateReference%22%3A+%7B%0D%0A++++++++%22link%22%3A+%22https%3A%2F%2Flocalhost%2Fmgmt%2Fcm%2Fcloud%2Ftenant%2Ftemplates%2Fiapp%2Ff5-http-lb%22%0D%0A++++%7D%2C%0D%0A++++%22vars%22%3A+%5B%0D%0A++++++++%7B%0D%0A++++++++++++%22name%22%3A+%22pool__addr%22%2C%0D%0A++++++++++++%22value%22%3A+%22192.168.2.10%22%0D%0A++++++++%7D%2C%0D%0A++++++++%7B%0D%0A++++++++++++%22name%22%3A+%22pool__port%22%2C%0D%0A++++++++++++%22value%22%3A+%2280%22%0D%0A++++++++%7D%0D%0A++++%5D%2C%0D%0A++++%22tables%22%3A+%5B%0D%0A++++++++%7B%0D%0A++++++++++++%22name%22%3A+%22pool__Members%22%2C%0D%0A++++++++++++%22columns%22%3A+%5B%0D%0A++++++++++++++++%22IPAddress%22%2C%0D%0A++++++++++++++++%22State%22%0D%0A++++++++++++%5D%2C%0D%0A++++++++++++%22rows%22%3A+%5B%0D%0A++++++++++++++++%5B%0D%0A++++++++++++++++++++%22192.168.3.5%22%2C%0D%0A++++++++++++++++++++%22enabled%22%0D%0A++++++++++++++++%5D%0D%0A++++++++++++%5D%0D%0A++++++++%7D%0D%0A++++%5D%2C%0D%0A++++%22properties%22%3A+%5B%0D%0A++++++++%7B%0D%0A++++++++++++%22id%22%3A+%22cloudConnectorReference%22%2C%0D%0A++++++++++++%22value%22%3A+%22https%3A%2F%2Flocalhost%2Fmgmt%2Fcm%2Fcloud%2Fconnectors%2Flocal%2F69c98650-af2d-4d83-8e1c-ce795dee82f0%22%0D%0A++++++++%7D%0D%0A++++%5D%0D%0A%7D```
