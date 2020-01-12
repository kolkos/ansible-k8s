Step                                        Master           Nodes
1. Change hostnames                         Yes              Yes
2. Install docker                           Yes              Yes

curl -sSL get.docker.com | sh
sudo usermod pi -aG docker
newgrp docker

3. Disable swap                             Yes              Yes

sudo dphys-swapfile swapoff
sudo dphys-swapfile uninstall
sudo update-rc.d dphys-swapfile remove
      
4. Change /boot/cmdline.txt                 Yes              Yes

cgroup_enable=cpuset cgroup_memory=1 cgroup_enable=memory

5. Reboot host                              Yes              Yes

6. Add dependecy to /etc/apt/sources.list.d/kubernetes.list

deb http://apt.kubernetes.io/ kubernetes-xenial main

7. Add the key for the dependency           Yes              Yes

sudo curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -

8. Update apt                               Yes              Yes

sudo apt update

9. Upgrade apt                              Yes              Yes

sudo apt upgrade
