# Kubesec Helm Chart

[![CI](https://github.com/abarrak/kubesec-helm/actions/workflows/lint.yaml/badge.svg)](https://github.com/abarrak/kubesec-helm/actions/workflows/lint.yaml/badge.svg)
[![Artifact Hub](https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/kubesec)](https://artifacthub.io/packages/helm/kubesec/kubesec)

## Features

Supports 3 modes to run the scanner: server, job, and cronjob.

1. **Deployment mode** (default): will run `kubesec` in server mode over `http` and make possible to send it workload for scanning interactively.

2. **job mode**: runs once scanning workload on all namespaces (default) or the specified ones.

3. **cron mode**: runs on specified schedule on all namespaces (default) or the specified ones.

## Usage

```bash
helm repo add kubesec https://abarrak.github.io/kubesec-helm
helm install kubesec-scanner kubesec/kubesec --version 1.0.0
```

To run in job mode (1 time basis):

```bash
helm install kubesec-scanner kubesec/kubesec --set mode=job
```

To run in cronjob periodically:

```bash
helm install kubesec-scanner kubesec/kubesec --set mode=cron
```

## Support

You can complement the chart with [the UI from here](https://github.com/abarrak/kubesec-ui) to visualize and analyze reports.

## License

MIT.
