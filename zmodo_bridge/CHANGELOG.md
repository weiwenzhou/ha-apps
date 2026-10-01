# 0.3.3

- A camera that returns an unexpected reply is tried again every five minutes
  instead of staying unavailable until the app is restarted. Other cameras
  keep streaming meanwhile.
- Security updates for the bundled cryptography library. The app now runs on
  Python 3.14.

# 0.3.2

- After an app restart, video and audio timestamps continue forward instead of
  starting over, so players that stayed connected through go2rtc no longer
  receive earlier timestamps. The app stores only each stream's last timestamp
  position in `/data/timeline.json`.

# 0.3.1

- Default `rtsp_port` is now 38554. The old default, 18554, is used by Home
  Assistant's built-in go2rtc, so serve mode could not start. Existing installs
  keep their saved value; change it to a free port if serve mode fails to start.
- Startup failures now log the operating-system error code (for example
  `EADDRINUSE`).

# 0.3.0

- Optional `output_mode: serve`: the bridge serves each camera on a loopback-only
  RTSP listener (`rtsp_port`, default 18554), so go2rtc needs one ordinary source
  per camera instead of an input plus a viewing name.
- `output_mode: publish` remains the default; existing configurations keep working.
- Per-minute sanitized stream status lines in the app log.

# 0.2.0 candidate

- Direct local H.264 video and optional PCMA audio publishing into existing go2rtc.
- Native RTSP publishing removes the MediaMTX and FFmpeg runtime dependencies.
- Independent camera retries and sanitized health metadata.
- Experimental release; sustained-playback acceptance remains under investigation.
