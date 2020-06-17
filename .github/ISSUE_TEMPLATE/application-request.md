---
name: Application Request
about: Request new applications using this template.
title: "[APP REQUEST]: "
labels: App Request
assignees: ''

---

### Dockerhub Link: ###
*replace with dockerhub link*

### Description ###
*replace with description*

### Separate Database? ###
*does this require a separate database in order to function?*

### Fill this out as best as you can. Documentation about these can be found here: https://www.portainer.io/documentation/how-to-use-templates/

```json
{
    "type": 1,
    "title": "Airsonic",
    "name": "airsonic",
    "description": "Airsonic is a free, web-based media streamer, providing ubiqutious access to your music. Use it to share your music with friends, or to listen to your own music while at work. You can stream to multiple players simultaneously, for instance to one player in your kitchen and another in your living room.",
    "logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/airsonic-logo.png",
    "image": "linuxserver/airsonic:latest",
    "categories": [
      "Music"
    ],
    "platform": "linux",
    "restart_policy": "unless-stopped",
    "ports": [
      "4040:4040/tcp"
    ],
    "volumes": [
      {
        "container": "/music",
        "bind": "/portainer/Music"

      },
      {
        "container": "/playlists",
        "bind": "/portainer/Files/AppData/Airsonic/Playlists"
      },
      {
        "container": "/podcasts",
        "bind": "/portainer/Podcasts"
      },
      {
        "container": "/media",
        "bind": "/portainer/Files/AppData/Airsonic/Media"
      },
      {
        "container": "/config",
        "bind": "/portainer/Files/AppData/Config/Airsonic/"
      }
    ],
    "env": [
      {
        "name": "PUID",
        "label": "PUID",
        "default": "1000"
      },
      {
        "name": "PGID",
        "label": "PGID",
        "default": "100"
      },
      {
        "name": "CONTEXT_PATH",
        "label": "CONTEXT_PATH",
        "set": "airsonic"
      },
      {
        "name": "JAVA_OPTS",
        "label": "JAVA_OPTS",
        "set": "-Xms256m -Xmx512m"
      }
    ]
  },
```
