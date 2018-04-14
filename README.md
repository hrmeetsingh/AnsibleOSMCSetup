# AnsibleOSMCSetup
To setup simple video streaming addons after installing OSMC/Kodi first time. 

__Note__ This setup is tested with OSMC v17.6 installation on a Raspberry Pi 3 for now.

## Pre-requisites
- OSMC successfully installed and basic configuration done (SSH enabled)
- Connected to wifi and accessible
- Default user(osmc) secured with the new password preferrably
- SSH key exchange between your laptop and OSMC SSH server. Refer [ssh-keygen and ssh-copy-id reference](https://www.ssh.com/ssh/keygen/) for SSH stuff. Typically, in this step, after generating the public and private key on your system, you need to run `ssh-copy-id -i ~/.ssh/<key_name>.pub osmc@<OSMC IP>` which will allow Ansible to do password-less ssh.


## Steps
- Clone the repository `git clone https://github.com/hrmeetsingh/AnsibleOSMCSetup.git`
- Edit the hosts file to make changes for the IP of OSMC server (My case, it is installed on an Raspberry Pi 3, so the name of host)
- Edit vars.yml file to set your region (some RaspberryPi setups require this to support all 802.11 b/g/n wifi channels read [this](https://singhbydivineright.wordpress.com/2018/03/12/kodi-osmc-does-not-connect-to-wifi-channel-12-13-fix-it-this-way/) blog for reference )
- Run the command `ansible-playbook -i hosts playbook.yml`

## What does it do?
Copies the youtube, dailymotion and kodil repository add-on zips to the OSMC server from where addons can be easily installed.

## TODO
- Installation of addons also automated from playbook
