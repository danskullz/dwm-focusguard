# focusguard

## Description

This patch keeps focus on a visible fullscreen client when focus would
otherwise move to a normal client. It applies to dwm 6.8.

When focus would move to a normal client, `focus()` checks that client's
monitor for a visible fullscreen client. If one exists, the fullscreen client
keeps focus and is raised above the blocked window. This covers newly managed
windows and other focus paths. The blocked client remains managed and can be
reached after the game leaves fullscreen or by switching tags.

## Configuration

The patch uses the existing `lockfullscreen` option in `config.h`. Set it to
0 to disable the behaviour. No new options are added.

## Testing

Applies and builds against dwm 6.8. Runtime tested under Xvfb. A new window
remained managed, but the fullscreen client kept X input focus, stayed
`_NET_ACTIVE_WINDOW`, and remained above the new window. Setting
`lockfullscreen` to 0 restored the original focus behaviour.

## Download

* [dwm-focusguard-6.8.diff](dwm-focusguard-6.8.diff)

## Author

* Daniel Guihot - [daniel@guihot.net](mailto:daniel@guihot.net)
