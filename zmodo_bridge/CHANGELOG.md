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
