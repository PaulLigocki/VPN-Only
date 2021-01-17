# VPN-Only
Ansible Playbook
* Disable IPv6
* Configure UFW Deny Incoming by default
* Configure UFW Deny Outgoing by default
* Configure UFW allow outgoing traffic via VPN interface
* Configure UFW allow incoming traffic via VPN interface OPTIONAL
## Prerequisites
* Ubuntu/Debian Linux O/S
* sudo apt update && sudo apt install ansible
* ansible-galaxy collection install community.general #To resolve url to ip address
## To Do
* Implement private DNS
## Usage
* Clone Repo
git clone https://github.com/PaulLigocki/VPN-Only.git
* Create overide vars.yml
nano ~/vars.yml
---\
  vars:\
    vpn_servers: #au.vpn.private:555
    - ip: 999.999.999.999\
      url: example.com\
      port: 555\
      proto: udp\
      name: au.vpn.private
    - ip: 888.888.888.888\
      url: example.com\
      port: 666\
      proto: udp\
      name: au.vpn.private

vpn_interface: wg0\
allow_imcoming: true
