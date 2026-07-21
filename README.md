# vfox-gcloud

Google Cloud SDK (gcloud CLI) plugin for [vfox](https://github.com/version-fox/vfox) and [mise](https://github.com/jdx/mise).

## Installation

### With mise

```bash
mise use -g vfox:gcloud@latest
```

### With vfox

```bash
vfox add gcloud
vfox install gcloud@latest
```

## Usage

### Install a specific version

```bash
# With mise
mise use gcloud@450.0.0

# With vfox
vfox install gcloud@450.0.0
```

### List available versions

```bash
# With mise
mise ls-remote gcloud

# With vfox
vfox search gcloud
```

## Post-Installation

After installation, you may need to initialize gcloud:

```bash
gcloud init
```

### Installing Additional Components

You can install additional SDK components:

```bash
gcloud components install kubectl
gcloud components install gke-gcloud-auth-plugin
gcloud components install cloud-sql-proxy
```

### Default Cloud SDK Components

You can define a set of Cloud SDK components to be installed automatically every
time a new gcloud version is installed. Create a file named
`.default-cloud-sdk-components` with one component ID per line.

The plugin searches for this file in the following locations (in order):

1. `$CLOUDSDK_CONFIG/.default-cloud-sdk-components` (defaults to `~/.config/gcloud/` on Unix or `%APPDATA%\gcloud\` on Windows)
2. `$HOME/.default-cloud-sdk-components`

Example `~/.default-cloud-sdk-components`:

```
alpha
beta
cloud-firestore-emulator
gke-gcloud-auth-plugin
```

## Supported Platforms

- Linux (x86_64, ARM)
- macOS (x86_64, ARM/Apple Silicon)
- Windows (x86_64)

## Environment Variables

This plugin sets the following environment variables:

| Variable | Description |
|----------|-------------|
| `PATH` | Includes the gcloud SDK bin directory |
| `CLOUDSDK_ROOT_DIR` | Points to the gcloud SDK installation directory |

## License

MIT
