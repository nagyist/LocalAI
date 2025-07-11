
+++
disableToc = false
title = "Installer options"
weight = 24
+++

An installation script is available for quick and hassle-free installations, streamlining the setup process for new users.

Can be used with the following command:
```bash
curl https://localai.io/install.sh | sh
```

Installation can be configured with Environment variables, for example: 

```bash
curl https://localai.io/install.sh | VAR=value sh
```

List of the Environment Variables:
| Environment Variable | Description                                                  |
|----------------------|--------------------------------------------------------------|
| **DOCKER_INSTALL**       | Set to "true" to enable the installation of Docker images.    |
| **USE_AIO**              | Set to "true" to use the all-in-one LocalAI Docker image.    |
| **USE_VULKAN**           | Set to "true" to use Vulkan GPU support.                     |
| **API_KEY**              | Specify an API key for accessing LocalAI, if required.       |
| **PORT**                 | Specifies the port on which LocalAI will run (default is 8080). |
| **THREADS**              | Number of processor threads the application should use. Defaults to the number of logical cores minus one. |
| **VERSION**              | Specifies the version of LocalAI to install. Defaults to the latest available version. |
| **MODELS_PATH**          | Directory path where LocalAI models are stored (default is /usr/share/local-ai/models). |
| **P2P_TOKEN** | Token to use for the federation or for starting workers see [documentation]({{%relref "docs/features/distributed_inferencing" %}}) |
| **WORKER** | Set to "true" to make the instance a worker (p2p token is required see [documentation]({{%relref "docs/features/distributed_inferencing" %}})) |
| **FEDERATED** | Set to "true" to share the instance with the federation (p2p token is required see [documentation]({{%relref "docs/features/distributed_inferencing" %}}))  |
| **FEDERATED_SERVER** | Set to "true" to run the instance as a federation server which forwards requests to the federation (p2p token is required see [documentation]({{%relref "docs/features/distributed_inferencing" %}}))  |

## Image Selection

The installer will automatically detect your GPU and select the appropriate image. By default, it uses the standard images without extra Python dependencies. You can customize the image selection using the following environment variables:

- `USE_AIO=true`: Use all-in-one images that include all dependencies
- `USE_VULKAN=true`: Use Vulkan GPU support instead of vendor-specific GPU support

## Uninstallation

To uninstall, run:

```
curl https://localai.io/install.sh | sh -s -- --uninstall
```

We are looking into improving the installer, and as this is a first iteration any feedback is welcome! Open up an [issue](https://github.com/mudler/LocalAI/issues/new/choose) if something doesn't work for you!