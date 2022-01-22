# ** Working on Templates after Forking from Qballjos **

Added more items from various other portainer templates, after searching the forks from Qbalijos

I would also like to eventually add the following container templates in the future 

Vikunja

Rocket.Chat

Kavita (added)

Koomga

MagicMirror2 (added)


# New Ubuntu Server Setup Instructions - Prep



* Commands to prep your system:

  Update the system:

  * sudo apt update

*** sudo apt upgrade

** If you want to Install Glances: 

*** sudo glances -w

** Install and test Docker:

*** sudo apt install docker.io

*** sudo systemctl enable docker

*** sudo systemctl start docker

*** sudo systemctl status docker

** Setup Portainer: 

*** sudo docker volume create portainer_data

*** sudo docker run -d -p 8000:8000 -p 9000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce



* In the Browser Setup: 

** You Should now be able to navigate to the IP of the VM or Ubuntu Machine, going to the portainer port 9000  http://IPADress:9000

** Do initial Portainer registration 

** Configure Endpoint Setting so that the IP is set to that of the Host (basically, set the IP to the same thing you used to connect) 
   *** (Click Endpoints, then click the name of your VM/Server, and adjust the IP in the noted space)

** Adjust your app template list to: https://raw.githubusercontent.com/mycroftwilde/portainer_templates/master/Template/template.json
   *** (Click Settings, then adjust the App Template URL, and Apply the Changes.) 





















Below is from Fork

# Portainer V2 Templates for Selfhosted Projects/Homelabs

This is a template focused on helping people spin up selfhosted services using Portainer.

### Portainer V1 Templates for Selfhosted Projects/Homelabs has moved to

url: `https://raw.githubusercontent.com/Qballjos/portainer_templates/master/V1 Template/template.json`
!!!This template will no longer be maintained!!!

### Prerequisites

1. A server/NAS with docker installed
2. A Portainer setup.

*Want something we don't have? Make an issue and we'll work on adding it*

### Installing

1. Login to your portainer setup go to settings
2. Enable Use external templates
3. Add the url: `https://raw.githubusercontent.com/Qballjos/portainer_templates/master/Template/template.json` then go to app templates and hit refresh at the top.

### Information
All templates are already configured to bind mount to various places on your drive. This branch works without the need for OMV. The following folders are all created in /portainer/

* **Files** - General file storage.
  * **AppData** - Subfolder where application data (unrelated to served data) is stored.
    * **Config** - Subfolder where configuration files for every container are stored.
* **Downloads** - Where bittorrent and usenet downloaders download files to.
* **TV** - Where tv shows are stored/moved to after downloaded.
* **Movies** - Where movies are stored/moved to after downloaded.
* **Music** - Where music is stored/moved to after downloaded.
* **Books** - Where books are stored/moved to after downloaded.
* **Comics** - Where comics are stored/moved to after downloaded.
* **Podcasts** - Where podcasts are stored/moved to after downloaded.
## App List

  - Adguard 
  - Airsonic 
  - Authelia 
  - Bazarr 
  - Beets 
  - Vaultwarden 
  - Booksonic 
  - Cops 
  - Calibre-web 
  - Chevereto 
  - Chowdown 
  - Code-server 
  - Codiad 
  - Couchpotato 
  - Daapd 
  - Dashmachine 
  - Davos 
  - Deemix 
  - Domoticz 
  - Duckdns 
  - Duplicati 
  - Emby 
  - EmbyStat 
  - Filebrowser 
  - Freshrss 
  - Gazee 
  - Guacamole 
  - Grocy 
  - Htpcmanager 
  - Headphones 
  - Heimdall 
  - Homer 
  - Huginn 
  - Invoice_ninja 
  - Jackett 
  - Jellyfin 
  - kodi-headless 
  - Lazylibrarian 
  - Letsencrypt / SWAG 
  - Librespeed 
  - Lidarr 
  - Lychee
  - Mariadb 
  - Mcmyadmin2 
  - Medusa 
  - Minetest 
  - Minisatip 
  - Mstream 
  - Murmur 
  - Musicbrainz 
  - Muximux 
  - Mylar 
  - Nzbget 
  - Nzbhydra2 
  - Nextcloud 
  - Nginx 
  - Nginx-proxy-manager 
  - Oscam 
  - Ombi 
  - Openvpn-as 
  - Organizr-v2 
  - Overseerr 
  - Owncloud 
  - Petio 
  - Photoshow 
  - Pihole 
  - Piwigo 
  - Plex 
  - Plexrequests 
  - Projectsend 
  - Protonmail-bridge 
  - Prowlarr 
  - Pydio 
  - Qbittorrent 
  - Quassel-core 
  - Radarr 
  - Reactive-resume 
  - Resilio-sync 
  - Rutorrent 
  - Sabnzbd 
  - Shiori 
  - Sickchill 
  - Sickgear 
  - Smokeping 
  - Snibox 
  - Sonarr 
  - Syncthing 
  - Tautulli 
  - Thelounge 
  - Tiddlywiki 
  - Tt-rss 
  - Transmission 
  - Transmission-openvpn 
  - Tvheadend 
  - Ubooquity 
  - Unifi-controller 
  - Watchtower 
  - Webgrabplus 
  - Whoogle 
  - Wikijs 
  - Yacht 
  - Youtubedl-material 
  - Znc 


## Contributing

If you wish to contribute make a pull request, create an issue, or email me.

## Authors
* **NASHosted** - *Current Work* - [NASHOSTED](https://github.com/nashosted)
* **SelfhostedPro** - *Current Work* - [SelfhostedPro](https://github.com/SelfhostedPro)
* **Jos Visser** - *Initial work* - [Qballjos](https://github.com/Qballjos)
* **xe-nvdk** - *template conversion to portainer V2* - [xe-nvdk](https://github.com/xe-nvdk)
* **tbiering** - *Termplate cleanup and typo fixes* - [tbiering](https://github.com/tbiering)

See also the list of [contributors](https://github.com/Qballjos/portainer_templates/graphs/contributors) who participated in this project.

## Acknowledgments

* LinuxServer.io for the old Template
* Inspiration being too lazy to create each container template manualy
* The team behind Portainer for there awesome product and support in the community
