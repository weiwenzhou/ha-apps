# Home Assistant apps

A personal Home Assistant app catalog. It contains only installation metadata
for private container images: the source repositories and images are private,
and adding this catalog alone does not give access to them. Supported
architecture: amd64.

## Installing

1. In Home Assistant's app store, open the Registries dialog and add `ghcr.io`
   with a GitHub username and a classic token with `read:packages` that can
   read the private packages. Credentials belong in HA's registry settings,
   never in this repository URL or in app options.
2. Add `https://github.com/weiwenzhou/ha-apps` through the Repositories dialog.
3. Install an app and configure it before starting it.

Each app version points to a matching private container tag. HA offers its
normal Update action when this catalog advertises a newer version; source
commits alone do not trigger an update. Each app's private release process
writes only that app's folder.

## Apps

### Zmodo Local Bridge (`zmodo_bridge/`)

Sends local camera H.264 video and optional PCMA audio to an existing go2rtc
app. It does not require MediaMTX or an NVR in its streaming path. The bridge
is experimental and is not a general Zmodo compatibility claim. Keep it stopped
until camera options and the existing go2rtc input names are configured.

### eufy-sdk bridge (floodlight) (`eufy_sdk_bridge_floodlight/`)

The eufy-sdk bridge with a patch for older floodlight cameras (T8420X, T8424)
that need unencrypted P2P commands for live video and light control. Rebuilt
automatically when eufy-sdk or the bridge releases. Enter the Eufy account in
the app's configuration after installation.
