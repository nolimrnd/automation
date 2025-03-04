AUTOMATION GUIDE

1. VMWare Rocky Linux
    Settings
    Memory: 8GB
    Processors: 4
    Hard Disk: 25GB
    Network Adapter: NAT

    Login: root
    Password: C1sc0123

    Command to check your IP Address
    ip a

2. Edit BASIC-CONFIG

  Console to CoreBaba, CUCM, Edge
  
    CoreBaba - Line 112-148
    CUCM - 173-192
    Edge - 217-244

    PASTE TO ALL
      config t
      ip domain-name rivanit.com
      username admin privilege 15 secret pass
      crypto key generate rsa
                       -->2048
      ip ssh version 2



3. Edit call.yml
    Comment out your ip address in the dial peer voice

4. Edit core.yml
5. Edit ospfedge.yml
6. Edit iphone.yml

7. Open SecureCRT --> Quick Connect --> SSH2 --> Hostname 208.8.8.128 (IP of Rocky Linux)
    Enter username: root
    Enter password: C1sc0123


    - Clone GITHUB
        git clone https://github.com/kdalonbalbaera/automation/
        pip install ansible-pylibssh



        SSH TO COREBABA (IN CMD ROCKY LINUX)
            ssh admin@10.21.1.4
            ssh-keygen -f "/root/.ssh/known_hosts"
            ssh admin@10.21.1.4
            Password: pass
            exit



        cd /etc/ansible
        ls
        nano hosts
        cd automation
        ansible-playbook core.yml



      SSH TO CUCM (IN CMD ROCKY LINUX)

        ssh admin@10.21.100.8
        Password: pass
        exit


      SSH TO EDGE (IN CMD ROCKY LINUX)

        ssh admin@10.21.21.1
        Password: pass
        exit


      ls
      ansible-playbook run_all.yml
