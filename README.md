# Zmodo Local Bridge for Home Assistant

This catalog contains installation metadata for a private bridge image.
Access to the private image is required; adding this catalog alone does not
provide that access. Supported architecture: amd64.

The bridge sends local camera H.264 video and optional PCMA audio to an existing
go2rtc app. It does not require MediaMTX or an NVR in its streaming path.
The runtime implementation and source repository are private.

The initial candidate is experimental. Sustained playback and recovery work
remain under investigation. This is not a general Zmodo compatibility claim.

To install an approved release, add registry credentials for ghcr.io in Home
Assistant's app store Registries dialog, then add this repository through its
Repositories dialog. Credentials belong in HA's registry settings, never in
this repository URL or app options. Install the app and keep it stopped until
camera options and the existing go2rtc input names are configured.

Each released manifest version points to a matching private container tag.
HA offers its normal Update action when the catalog advertises a newer version.
Source commits alone do not trigger an installed app update.
