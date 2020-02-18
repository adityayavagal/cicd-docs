# PM2 and Jenkins Integration

1. **Login to your Jenkins Server via SSH**
2. **Change to Jenkins user using command**

    ```bash
    sudo su jenkins
    cd
    ```

3. **Generate ssh key**

    ```bash
    ssh-keygen
    ```

4. **Display and copy the public key to Deployment Server in .ssh/authorized_keys file**

    ```bash
    cat ~/.ssh/id_rsa.pub
    ```

5. **In your Jenkins Build Job in Build Section add "Execute shell" option and enter below command**

    ```bash
    # pm2 deploy ecosystem.config.js <env_you_want_to_run>
    pm2 deploy ecosystem.config.js production
    ```

## Ref

1. For ecosystem.config.js refer [documentation](https://pm2.keymetrics.io/docs/usage/application-declaration/) or [deployment](https://pm2.keymetrics.io/docs/usage/deployment/) 