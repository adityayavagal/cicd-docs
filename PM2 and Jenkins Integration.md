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
