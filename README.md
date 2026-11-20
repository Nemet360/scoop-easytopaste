# Scoop bucket — EasyToPaste

```powershell
scoop bucket add easytopaste https://github.com/Nemet360/scoop-easytopaste
scoop install easytopaste
easytopaste send "the thing you were about to paste into Teams"
```

Share a password, an API key or a note through a **one-time link**. Your
terminal encrypts it before anything leaves (AES-256-GCM); the key travels in
the link's URL fragment, which no HTTP client transmits, so the service stores
ciphertext it cannot read. The link dies on first read.

What it is: <https://easytopaste.com/?utm_source=scoop&utm_medium=cli&utm_campaign=launch-2026-11>
· how the encryption works: <https://easytopaste.com/how-it-works/?utm_source=scoop&utm_medium=cli&utm_campaign=launch-2026-11>

## What this bucket does

It unpacks the published npm tarball and writes a one-line `.cmd` shim that
runs it with Node and sets `EASYTOPASTE_CHANNEL=scoop`. The channel is the only
way a Scoop install is distinguishable on the service side — an install
followed by a command produces no page view, so a link tag cannot measure it.
Nothing else is sent: no plaintext, no key, no path, no telemetry.

The channel field reaches the service from **version 0.1.2 onward**; 0.1.1, the
version this manifest pins today, ignores it.

`checkver` and `autoupdate` point at the npm registry, so the manifest follows
new versions without a human editing a hash.
