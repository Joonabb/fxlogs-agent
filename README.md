# FXLogs agent releases

Signed release files of the FXLogs agent: the host service that runs a FiveM server's
FXServer for [FXLogs](https://fx.lossantos.fi). The source lives elsewhere; this repository
holds only releases.

Each release carries:

| File | What |
|---|---|
| `fxlogs-agent-linux-x64-<version>.tgz` | the agent and its Node runtime |
| `….tgz.sha256`, `….tgz.sig` | its SHA-256, and an Ed25519 signature by the FXLogs release key |
| `install.sh` | the installer |
| `version.txt`, `release.json` | the version, and the entry agents update from |

Install from the dashboard (Settings › Server control › Install the agent), which gives a
one-time code:

```sh
curl -fsSL https://github.com/Joonabb/fxlogs-agent/releases/latest/download/install.sh | sudo sh -s -- --code XXXX-XXXX-XXXX --api https://…
```

The installer verifies the bundle's SHA-256 and signature against the release key pinned in
it before anything from the bundle runs, and the agent does the same for every update.
