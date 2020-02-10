# pm2 Tool Deploy to remote server

**Command:** ```pm2 <config_file> <environment> ```
**Example:** ```pm2 <config_file> <environment> ```

## Config file options
| Entry name | Description | Type | Default |
|--|--|--|--|
| key | SSH key path | String | $HOME/.ssh |
| user | SSH user | String |
| host | SSH host | [String] |
| ssh_options | SSH options with no command-line flag, see ```man ssh``` | String or [String] |
| ref | GIT remote/branch | String |
| repo | GIT remote | String |
| path | path in the server | String |
| pre-setup | Pre-setup command or path to a script on your local machine | String |
| post-setup | Post-setup commands or path to a script on the host machine | String |
| pre-deploy local | pre-deploy action | String |
| post-deploy | post-deploy action | String |

## Simple deployment using pm2

1. **config.json**

```json
{
   "apps" : [{
      "name" : "HTTP-API",
      "script" : "http.js"
   }],
   "deploy" : {
     // "production" is the environment name
     "production" : {
       "user" : "ubuntu",
       "host" : ["192.168.0.13"],
       "ref"  : "origin/master",
       "repo" : "git@github.com:Username/repository.git",
       "path" : "/var/www/my-repository",
       "post-deploy" : "npm install; grunt dist"
      },
   }
}
```

2. **Generate ssh key and copy to server** (make sure you the public on your local machine for the key generated).

```bash
ssh-keygen -t rsa
ssh-copy-id node@myserver.com
```

3. **Now initialize the remote folder with:**

```bash
pm2 deploy <configuration_file> <environment> setup
```
Example:
```bash
pm2 deploy config.json production setup
```

4. **Deploy the code**

```bash
pm2 deploy ecosystem.json production
```

**Note:** For help try ```pm2 deploy help```

## References:
1. [pm2 Single Page Doc ](https://pm2.keymetrics.io/docs/usage/pm2-doc-single-page/)
2. [pm2 Deployment](https://pm2.keymetrics.io/docs/usage/deployment/)
