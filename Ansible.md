# Ansible

- Ansible is an IT automation tool. It can configure systems, deploy software, and orchestrate more advanced IT tasks such as continuous deployments or zero downtime rolling updates.
- It's an Agentless tool, which means you don't have to install it anywhere except your controller machine(machine from which you access your hosts).
- It is CLI based and configurations are pushed using ansible-playbooks these are nothing but yml files which contain configurations.
- The host list and configurations are maintained inventory.

## Use Cases

- **Provisioning**
  - Your apps have to live somewhere. If you’re PXE booting and kickstarting bare-metal servers or VMs, or creating virtual or cloud instances from templates, Ansible and Red Hat® Ansible® Tower help streamline the process.
- **Configuration Management**
  - Centralizing configuration file management and deployment is a common use case for Ansible, and it’s how many power users are first introduced to the Ansible automation platform.
- **Application Deployment**
  - When you define your application with Ansible, and manage the deployment with Ansible Tower, teams are able to effectively manage the entire application lifecycle from development to production.
- **Continuous Delivery**
  - Creating a CI/CD pipeline requires buy-in from numerous teams. You can’t do it without a simple automation platform that everyone in your organization can use. Ansible Playbooks keep your applications properly deployed (and managed) throughout their entire lifecycle.
- **Security Automation**
  - When you define your security policy in Ansible, scanning and remediation of site-wide security policy can be integrated into other automated processes and instead of being an afterthought, it’ll be integral in everything that is deployed.
- **Orchestration**
  - Configurations alone don’t define your environment. You need to define how multiple configurations interact and ensure the disparate pieces can be managed as a whole. Out of complexity and chaos, Ansible brings order.

## Ansible Components

1. **Ansible Playbook**
   - Playbooks are Ansible’s configuration, deployment, and orchestration language. They can describe a policy you want your remote systems to enforce, or a set of steps in a general IT process.
2. **Ansible Tower**
   - Red Hat Ansible Tower is a web console and REST API for operationalizing Ansible across your team, organization, and enterpise. It’s designed to be the hub for all of your automation tasks.
3. **Ansible Network**
   - Ansible Network modules extend the benefits of simple, powerful, agentless automation to network administrators and teams. Ansible Network modules can configure your network stack, test and validate existing network state, and discover and correct network configuration drift.
4. **Ansible Lint**
   - Ansible Lint is a commandline tool for linting playbooks. Use it to detect behaviors and practices that could potentially be improved.
5. **Ansible Galaxy**
   - Galaxy is a hub for finding and sharing Ansible content.

## References

1. [Ansible Documentation](https://docs.ansible.com/ansible/latest/index.html)
2. [Ansible Use Cases](https://www.ansible.com/use-cases)
3. [How Ansible Works](https://www.ansible.com/overview/how-ansible-works)
4. [Ansible Playbooks](https://docs.ansible.com/ansible/latest/user_guide/playbooks.html)
