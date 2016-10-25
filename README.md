# reprot

## Reproducing the failure

1. Create a Web app _App Service_ on Azure
2. Enable _Local Git Repository_ deployment
3. Set the necessary environment variables

        HUBOT_ADAPTER=slack
        HUBOT_SLACK_TOKEN=<slack-token>

3. Deploy

        git remote add azure https://<deployment-user>@<site-name>.scm.azurewebsites.net:443/<site-name>.git
        git push azure master

## How this project was created

1. `yo hubot`
2. `rm Procfile`
3. Remove unused heroku and redis modules from external-scripts
4. `npm uninstall hubot-heroku-keepalive hubot-redis-brain --save`
5. `azure site deploymentscript --node`
6. Add a step to deploy.sh to create hubot script with coffee extension
7. Create server.js to start hubot

