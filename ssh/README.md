# Faith FM SSH/terminal addon

A clone of HA-community's "Advanced SSH & Web Terminal" [add-on](https://github.com/hassio-addons/addon-ssh).

Config changes:
* Disable audio - to work with the audio-plugin-disabled version of the HA supervisor.
* Disable services: mysql + mqtt
* Change defaults:
  * port: 22777
  * user: hassio -> root  (required for SFTP to work)
  * sftp: enabled

Dockerfile changes:
* Remove pulseaudio package
* Add mpc package
