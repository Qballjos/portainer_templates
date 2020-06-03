
# Portainer Templates for Selfhosted Projects/Homelabs

This is a template focused on helping people spin up selfhosted services using Portainer.

### Prerequisites

1. A Server running OMV (Not 100% required but folders will be created in /srv/dev-disk-by-label-media if not installed)
2. The following folders:
  * Files (required)
  * Downloads
  * TV
  * Movies
  * Music
  * Books
  * Comics
  * Podcasts
3. A Portainer setup.

### Installing

1. Login to your portainer setup go to settings 
2. Enable Use external templates
3. Add the url: `https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Template/template.json` then go to app templates and hit refresh at the top.

### Information
All templates are already configured to bind mount to various places on your drive. The initial build is for use with OpenMediaVault v5. The following folders are all created in /srv/dev-disk-by-label-media/

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

## Contributing

If you wish to contribute make a pull request, create an issue, or email me.

## Authors
* **NASHosted** - *Current Work*
* **SelfhostedPro** - *Current Work*
* **Jos Visser** - *Initial work* - [Qballjos](https://github.com/Qballjos)

See also the list of [contributors](https://github.com/SelfhostedPro/selfhosted_templates/contributors) who participated in this project.

## Acknowledgments

* LinuxServer.io for the old Template
* Inspiration being to lazy to create each container template manualy
