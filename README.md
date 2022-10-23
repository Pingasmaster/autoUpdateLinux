# autoUpdateLinux: About

AutoUpdateLinux is a set of instructions to automatically update Debian or Arch linux on startup, to ease up the jobs of sysadmins. So to fix any problem you might have on your server, just reboot, then it will apply updates, and reboot again and you're good to go! Normal people might not see the convenince of this script but sysadmins does.

##Debian

##### Prerequisites

We just need git and updates (of course!)

```sh
# Install updates
sudo apt update && sudo apt upgrade
# install git
sudo apt install git
```

##### Download

Login as a user to do the following steps, not as root!

```sh
# Got to your home directory
cd ~
# Clone project
git clone https://github.com/Pingasmaster/autoUpdateLinux/
# Enter folder & look around
cd autoUpdateLinux/ && ls
# Give correct permissions to files
sudo chmod 700 updates-debian.sh
sudo chmod +x updates-debian.sh
# Create systemctl service
sudo mv update-debian.service /etc/systemd/system/update.service
# Add service at startup and start it now for a test
sudo systemctl enable update
sudo systemctl start update
# Wait a bit for the script to launch before testing its output with this command
sudo systemctl status update
```
Here it is, everything is set up!
For more on systemctl startup services, you can read ```https://linuxhint.com/run-script-debian-11-boot-up/```.
