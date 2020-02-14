# Simple Ansible Playbook Tutorial

**Note:** This example uses Linux ubuntu as controller machine and the host machine is also a ubuntu machine in Amazon AWS.

**Prerequisites:** Create an AWS EC2 to instance and make sure you have the ssh key to access it remotely.

------

1. **Download and install ansible**

   ```bash
   sudo apt update
   sudo apt install software-properties-common
   sudo apt-add-repository --yes --update ppa:ansible/ansible
   sudo apt install ansible  
   ```

2. **Create Simple Inventory**

   ```bash
   sudo nano /etc/ansible/hosts
   ```

   Enter the following lines into file and save.

   ```ini
   #Group name
   [test-server]
   #Host List your server ip or domain name
   192.168.0.1
   ```

3. **Ping the hosts**

   ```bash
   ansible -m ping test-server
   ```

   Response should be similar to given below

   ```json
   192.168.0.1 | SUCCESS => {
   	"changed": false,
   	"ping": "pong"
   }
   ```

4. **Create a playbook**

   ```yaml
   ---
   - hosts : test-server
     become : true
     tasks :
     - name : install nginx
       package : pkg=nginx state=installed

       notify :
         - start nginx

     handlers :
       - name : start nginx
         service : name=nginx state=started
   ```

5. **Running Playbook**

   ```bash
   ansible-playbook playbook_name.yml --key-file "<path_to_key>"
   ```

**References:**

1. [Ansible Installation](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)
2. [Video Tutorial](https://youtu.be/4nKW2eF-nIw)
3. [Ansible Playbook Doc](https://docs.ansible.com/ansible/latest/user_guide/playbooks_intro.html)
