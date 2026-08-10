# OpenObserve for LazyCat

LazyCat LPK v2 packaging for [OpenObserve](https://github.com/openobserve/openobserve).

## Runtime

- Package ID: `community.lazycat.app.openobserve`
- Image: `ghcr.1ms.run/openobserve/openobserve-dev:v0.92.0-rc1-b31ff6c`
- Platform: `linux/amd64`
- Web port: `5080`
- Persistent data: `/lzcapp/var/data` → `/data`

The installation wizard asks for the administrator email and password. The login page uses LazyCat's password injection to fill and submit those credentials automatically.

OpenObserve supports importing and exporting configuration and data. The bundled LazyCat file chooser integration exposes both local-device and LazyCat storage choices for browser file operations.

## Build

```bash
lzc-cli project release -o dist/application.lpk
```

Pushing a `v*` tag runs the reusable LazyCat workflow, creates a versioned GitHub Release asset, and publishes only to the configured MiaoMiao private store. Official LazyCat store publishing is disabled.

Required GitHub Secrets are `APPSTORE_URL` and `APPSTORE_TOKEN`; `APP_ID` and `PRIVATE_STORE_GROUP_CODES` are optional.
