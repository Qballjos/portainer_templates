# WiP - Portiner V2 Template after Forking from Qballjos - WiP

Added more items from various other portainer templates, after searching the forks from Qballjos

I would also like to eventually add the following container templates in the future:

 - Vikunja

 - Rocket.Chat

 - Kavita (Added Config, after reviewing docker setup notes)

 - Koomga (Added Config, after reviewing docker setup notes)

 - MagicMirror2 (Added Config, after reviewing docker setup notes)

 - Readarr (Added Config, after reviewing docker setup notes)

  Further to the above, Catagory Placement work will be on-going...Some images will also be updated, and the code formatting will be adjusted for cleanliness... I feel tired already... hahaha 
 
 
### Useful Supplimental Software Links: 

* [Putty](https://www.chiark.greenend.org.uk/~sgtatham/putty/)
* [7zip](https://www.7-zip.org/download.html)
* [VNC Viewer](https://www.realvnc.com/en/connect/download/viewer/)
* [Draw.io](https://www.draw.io)
  
  
  
## New Proxmox Host - Prep

 One of the best ways to host your servers is on an older machine you may have lying around. You can flash it/image it with Proxmox, and Proxmox will allow you to use all the hardware in your older machine for a number of little servers, as virtual machines, within proxmox itself. 
 
 * Prep the hardware -> Clean it, if needed. 
 
 * Flash a USB stick with an image from the Proxmox website: [Proxox Website](https://www.proxmox.com/en/downloads)
 
 * Image your old computer -> Have the computer boot from the USB stick, instead of it's internal harddrive, and then install Proxmox
 
 * After doing all of the install steps, reboot the machine at the noted time in the install instructions, and then navigate to your management interface. Often times, it's:
  
    * https://IPAddress:8006/  


## New Ubuntu Server/VM Setup Instructions - Prep

### Where to get the OS image:

* [Ubuntu Desktop](https://ubuntu.com/download/desktop)

* [Ubuntu Server](https://ubuntu.com/download/server)


### Commands to prep your system, after Install:

  Update the system:

  * sudo apt update

  * sudo apt upgrade

  If you want to Install Glances: 

  * sudo glances -w

  If you want to Install CFIS Utilities to Map Network Shares: 

  * sudo apt-get install cifs-utils

  Install and test Docker:

  * sudo apt install docker.io

  * sudo systemctl enable docker

  * sudo systemctl start docker

  * sudo systemctl status docker

  Setup Portainer: 

  * sudo docker volume create portainer_data

  * sudo docker run -d -p 8000:8000 -p 9000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce

** How to Update Portainer, for when needed: **

  * sudo docker stop portainer
  
  * sudo docker rm portainer
  
  * sudo docker pull portainer/portainer-ce
  
  * sudo docker run -d -p 8000:8000 -p 9000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce



** Further Ubuntu Setup items to be Added at a Later Time: **

   ## Supplemental steps for a PiHole Container, Ubtuntu Server
   
   After pulling the container image, and it failing to start, make the following adjustments: 

   * sudo systemctl stop systemd-resolved.service

   * sudo systemctl disable systemd-resolved.service

   Next, run the below and edit the name server:

   * sudo nano /etc/resolv.conf

   You can change the name server to OpenDNS normally

   * 208.67.222.222
   * 208.67.220.220

   ## Supplimental Setup Notes
   
   Commands for Mapping a Network Share, after installing the CFIS Utilities
   
   (Please note: This is from some old notes of mine, and it will probably need to be reviewed to be sure it's within best practices)

   * sudo mkdir /mnt/*FolderNameonyourUbuntuSystem*
   * sudo chown -R nobody:nogroup /mnt/*FolderNameonyourUbuntuSystem*
   * sudo chmod -R 0755 /mnt/*FolderNameonyourUbuntuSystem*
   * sudo mount.cifs //*IPAddressofNetworkShare*/*ShareName* /mnt/*FolderNameonyourUbuntuSystem* -o user=*UbuntuUser*,uid=1000
      * Enter Applicable Passwords  

   ### Further Ubuntu Setup items to be Added at a Later Time:

   1. Adding a public SSH Key to your Server 

   2. Mapping a Network Share for Container Access (Media/Library Files on a NAS, Backup Locations, etc)

   3. Remapping a Share at Server Boot

   4. Securing your Servers



## In the Browser Setup: 

  You Should now be able to navigate to the IP of the VM or Ubuntu Machine, going to the portainer port 9000  http://IPADress:9000

  Do initial Portainer registration 

  Configure Endpoint Setting so that the IP is set to that of the Host (basically, set the IP to the same thing you used to connect) 
      - Click Endpoints, then click the name of your VM/Server, and adjust the IP in the noted space

  Adjust your app template list to: https://raw.githubusercontent.com/mycroftwilde/portainer_templates/master/Template/template.json
      - Click Settings, then adjust the App Template URL, and Apply the Changes. Afterword, navigate back to the app templates and the list should refesh to be pulling from this repository


 ## ** Helpful Links and URLs for Self-Hosting **
 
  * [LinuxServer.io](https://www.linuxserver.io/)

  * [Porkbun](https://porkbun.com)

  * [Cloudflare](https://www.cloudflare.com/)

  * [SiteGrounds](https://www.siteground.com/)

  * [Hotio.Dev](https://hotio.dev/)

  * [PfSense](https://www.pfsense.org/download/)

  * [Awesome Self-Hosted's Git Page](https://github.com/awesome-selfhosted/awesome-selfhosted)
  
  * [New Proxmox Host and Home Assistant Setup, Document and Video Guide - By JaunMTech](https://www.juanmtech.com/install-proxmox-and-virtualize-home-assistant/)


 ## A Note about Dashboard Servers

Often you can create a server version of something you'd like to display on a wall display at home, and then use a raspberry pi to connect to that webpage on boot automatically. You can use this set of instructions, and just substitute out the dakboard specific elements, and use it to setup a raspberry pi to connect automatically to one of your running dashboard containers' URL. 

[Instructions](https://blog.dakboard.com/diy-wall-display/)

 # Adding Further Containers: What I'm currently looking for
 
 I'm currently wanting to add the following containers 
 
 * Rocket.Chat

 * Habitica

 * Vikunja

  If you'd like to assist with the above, please get into contact and I'll see about adding the applicable code to expand the list 
  
  Note: any supplimental setup notes can be placed in the description -> Habitica, I'm thinking, would probably need this.

# ** From the Forked Authors Notes ** 

Previous Authors
* **NASHosted** - *Current Work* - [NASHOSTED](https://github.com/nashosted)
* **SelfhostedPro** - *Current Work* - [SelfhostedPro](https://github.com/SelfhostedPro)
* **Jos Visser** - *Initial work* - [Qballjos](https://github.com/Qballjos)
* **xe-nvdk** - *template conversion to portainer V2* - [xe-nvdk](https://github.com/xe-nvdk)
* **tbiering** - *Termplate cleanup and typo fixes* - [tbiering](https://github.com/tbiering)

See also the list of [contributors](https://github.com/Qballjos/portainer_templates/graphs/contributors) who participated in this project.

# My Notes

Other Templates that items were discovered/pulled from will be added when time allows. A various list of other templates have been noted below where some items have been sourced. 

[technorabilia](https://raw.githubusercontent.com/technorabilia/portainer-templates/main/lsio/templates/templates-2.0.json)

[mikestraney](https://raw.githubusercontent.com/mikestraney/portainer-templates/master/templates.json)


# * Mental Health *

 As a side note, not related, I'm a large advocate of Mental Health. If you are having a rough time right now, please see my Mental Health Youtube Playlist:
 
 [Mental Health Youtube Playlist](https://youtube.com/playlist?list=PLGk2on7ccZONCobYxwGdvwMcF43gIKmqk)
 


