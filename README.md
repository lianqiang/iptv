# IPTV Playlist

A maintained M3U playlist for APTV and other IPTV players. It combines local IPTV multicast relays with selected public internet streams.

## Playlist

- File: [`IPTV-Mobile.m3u`](./IPTV-Mobile.m3u)
- Subscription URL: `https://raw.githubusercontent.com/lianqiang/iptv/refs/heads/main/IPTV-Mobile.m3u`
- Current size: 169 channels
- Local streams: 79 channels routed through `192.168.10.1`
- Public streams: 90 channels
- Metadata: every channel includes a display logo and category

Local streams require access to the configured home network and IPTV relay. Public streams may be unavailable in some regions or may change without notice.

## Use with APTV

1. Open **Config Center** in APTV.
2. Add a subscription and paste the subscription URL above.
3. Save the configuration and select **Refresh**.
4. Use APTV's channel search to verify playback.

The playlist includes an XMLTV EPG URL in its `#EXTM3U` header. Compatible players should load it automatically.

## Channel Groups

The playlist is organized into 14 player-friendly groups:

- 央视, 卫视, 北京, CGTN, and 4K
- 港澳 and 台湾
- 国际新闻 and 国际综合
- 纪录, 生活, 体育, 电影, and 少儿

Each entry includes `tvg-name`, `tvg-logo`, and `group-title` metadata where applicable. EPG names are kept compatible with the configured XMLTV source.

## Maintenance

Public streams are tested in the macOS APTV app. Direct HLS renditions are preferred when master playlists or redirect endpoints are incompatible with APTV.

When editing the playlist:

- Keep each `#EXTINF` entry immediately followed by one stream URL.
- Confirm that the number of `#EXTINF` entries matches the number of stream URLs.
- Keep `tvg-logo` and `group-title` metadata present on every channel.
- Reject test cards, no-signal feeds, and streams carrying a different channel.
- Prefer stable HTTPS sources and exact channel matches.

## Disclaimer

This repository does not host or retransmit video. It only contains links to streams provided by third parties. Channel names, logos, EPG data, and broadcasts belong to their respective owners. Availability, quality, and geographic access are controlled by the stream providers.

## License

The repository content is available under the [MIT License](./LICENSE). The license does not grant rights to third-party broadcasts, trademarks, logos, or EPG data referenced by the playlist.
