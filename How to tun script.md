explain script:

bashscript that helps install a master and slave ubuntu vagrant machine and runs LAMP stack

Must have: 

- vagrant 
- virtual box 


slave & master:
    memory: 1024
    cpus: 2


slave machine: 
 spec:
    name = slave1
    image = ubuntu/focal64
    network:
        private_network 
        constant ip: "192.168.20.11"

slave configuration:
    update & upgrade machine

    install:
        - sshpass: allows you to chip in the password while logging in
        - switching the password authenticator on to loggin using password
        - restarting the sshd service
        - installing avahi-daemon libnss-mdns





master machine: 
    spec: 
        Host name = master
        image = ubuntu/focal64
        network:
          private_network 
          constant ip: "192.168.20.10"

master configuration:
    update & upgrade machine

    install:
        - sshpass: allows you to chip in the password while logging in
        - switching the password authenticator on to loggin using password
        - restarting the sshd service
        - installing avahi-daemon libnss-mdns


script configuration for master:
- creating a sudo user named "altschool"
- creating ssh key for the user "altschool"
- copy the user "altschool" ssh to the slave machine (only the user altschool should be able to ssh into the slave machine with a password)
- copy a file named "/mnt" from the "altschool" user to the slave machine.


LAMP stack (master & slave installation):
    LAMP: (linux, apache, mysql & php):
        - Installing Apache2 Web server
        - Installing PHP & Requirements
        - Installing MySQL
        - Enabling Modules
        - Restarting Apache


lastly a LAMP stack will be intalled on both master and slave once the scrip runs. apache is going to be restarted after installation and configuration. 

also mysql server and client are going to be installed on both master and slave

different versions of php is going to be installed and permissions for /var/www is going to be set to an owner and group of "www-data:www-data"

