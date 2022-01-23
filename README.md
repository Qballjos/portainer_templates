# WiP - Working on Portiner V2 Template after Forking from Qballjos - WiP

Added more items from various other portainer templates, after searching the forks from Qballjos

I would also like to eventually add the following container templates in the future:

 - Vikunja

 - Rocket.Chat

 - Kavita (Added Config, after reviewing docker setup notes)

 - Koomga (Added Config, after reviewing docker setup notes)

 - MagicMirror2 (Added Config, after reviewing docker setup notes)

 - Readarr (Added Config, after reviewing docker setup notes)

  Further to the above, Catagory Placement work will be on-going...Some images will also be updated, and the code formatting will be adjusted for cleanliness... I feel tired already... hahaha 

## New Ubuntu Server Setup Instructions - Prep



### Commands to prep your system:

  Update the system:

  * sudo apt update

  * sudo apt upgrade

  If you want to Install Glances: 

  * sudo glances -w

  Install and test Docker:

  * sudo apt install docker.io

  * sudo systemctl enable docker

  * sudo systemctl start docker

  * sudo systemctl status docker

  Setup Portainer: 

  * sudo docker volume create portainer_data

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






















## ** From the Forked Authors Notes ** 

Previous Authors
* **NASHosted** - *Current Work* - [NASHOSTED](https://github.com/nashosted)
* **SelfhostedPro** - *Current Work* - [SelfhostedPro](https://github.com/SelfhostedPro)
* **Jos Visser** - *Initial work* - [Qballjos](https://github.com/Qballjos)
* **xe-nvdk** - *template conversion to portainer V2* - [xe-nvdk](https://github.com/xe-nvdk)
* **tbiering** - *Termplate cleanup and typo fixes* - [tbiering](https://github.com/tbiering)

See also the list of [contributors](https://github.com/Qballjos/portainer_templates/graphs/contributors) who participated in this project.

## ** My Notes **

Other Templates that items were discovered/pulled from will be added when time allows. A various list of other templates have been noted below where some items have been sourced. 

[technorabilia](https://raw.githubusercontent.com/technorabilia/portainer-templates/main/lsio/templates/templates-2.0.json)

[mikestraney](https://raw.githubusercontent.com/mikestraney/portainer-templates/master/templates.json)

