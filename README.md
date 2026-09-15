# focusguard

## Description

This patch keeps focus on a fullscreen client when a new window appears. It
applies to dwm 6.8.

`manage()` calls `focus(NULL)` for every new client on the selected monitor,
so Steam update dialogs, chat windows and notifications pull focus off a
running fullscreen game. Many games then drop fullscreen. With this patch the
fullscreen client stays selected and focused. The new client is still
attached, arranged and mapped, and can be reached after the game leaves
fullscreen or by switching tags.

## Configuration

The patch uses the existing `lockfullscreen` option in `config.h`. Set it to
0 to disable the behaviour. No new options are added.

## Testing

Applies and builds against dwm 6.8. Runtime tested under Xvfb: with a
fullscreen client focused, a new window no longer becomes
`_NET_ACTIVE_WINDOW`.

## Download

* [dwm-focusguard-6.8.diff](dwm-focusguard-6.8.diff)

## Author

* Daniel Guihot - [daniel@guihot.net](mailto:daniel@guihot.net)
