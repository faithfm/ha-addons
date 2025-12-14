# MPD addon (FFM)

A clone of Poeschl's MPD [add-on](https://github.com/Poeschl-HomeAssistant-Addons/mpd).

Poeschl's addon uses HA's normal PulseAudio device which has been intentionally disabled in our audio-plugin-disabled custom version of the HA supervisor.  Our forked plugin passes ALSA's low-level /dev/snd device through to the container instead.

Config changes:
* Disable "audio"                        (ie: PulseAudio plugin dependency)
* Disable "devices" mapping              (HA's legacy "devices" mapping has not been supported for a while)
* Pass /dev/snd device to the container:
  * Enable raw_devices /dev/snd mapping  (raw_devices is defined in our custom HA supervisor)
  * Enable full_access                   (required for raw_devices to work)
  * Disable apparmor                     (required for raw_devices to work)
* Disable "image" (temporary)
* Bump version:  dev (repo) -> 1.8.2 (actual fork version) -> 1.8.2.1 (indicating our changes))

MPD config changes:
* Replace output: PulseAudio -> First ALSA device

Dockerfile changes:
* Add "alsa-utils" package               (for convenience)
