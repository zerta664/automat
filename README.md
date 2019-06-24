# Ansible Roles: JCasC, Nexus 3 OSS

These roles install and configure Jenkins(JCasC) , Jenkins slave node, Nexus Repository 3.16  on CentOS/RHEL.

## Role Variables


Ansible variables, which must be changed

file nexus.yml
 
  nexus_admin_password: "your_pass_for_nexus_admin"
  nexus_local_users:
      - username: jenkins #
        password: "your_pass_for_local_nexus_user"


file roles/jenkins_config/files/jenkins.yaml

   - id: "admin"
     password: "your_pass_for_admin_jemkins"
  

    description: "key for jenkins_slave"
          id: "5"
          username: jenkins
          privateKeySource:
            directEntry:
              privateKey: |- "your private_key for slave"


    username: "admin"
    password: "your_pass_for nexus_admin"
   
   file jenkins_slave.yml
       master_host: your_master_host
       slave_jenkins_cred_id: 5
       slave_jenkins_username: jenkins
       slave_jenkins_public_key: your_public_key


