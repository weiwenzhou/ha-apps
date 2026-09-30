# Configuration and updates

Enter each camera's confirmed LAN address and device ID in this app's HA
configuration. Keep deployment options and credentials private.

Publish to empty go2rtc input streams, for example camera_one_input. Configure
each viewing name, for example camera_one, as a local RTSP pull of its input.
Choose stream names that match your own installation. Preserve unrelated
go2rtc settings and review any required restart.
The default RTSP destination is the HA host's existing listener on port 8554.

With `output_mode: serve`, the bridge instead listens on the HA host's loopback
address at `rtsp_port` (default 38554; do not use 18554, which Home Assistant's built-in go2rtc uses). Configure each viewing name as a pull of
rtsp://127.0.0.1:38554/CAMERA_NAME, where CAMERA_NAME is the camera's name in this
app's options, and remove its separate input stream. Change the go2rtc
configuration and this option together; streams are unavailable in between.

Only one bridge instance should publish the same input names. For migration
from a local app, keep the old app stopped, install this repository app and copy
its configuration in HA. Preserve the old configuration for rollback. Validate
all streams before removing the previous installation.

Update from the app page in Home Assistant after reviewing the release notes.
A private registry credential must remain valid for downloads. Streaming after
installation uses the LAN and does not need registry access.
