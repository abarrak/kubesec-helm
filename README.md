# Kubesec Helm Chart

[![CI](https://github.com/abarrak/kubesec-helm/actions/workflows/lint.yaml/badge.svg)](https://github.com/abarrak/kubesec-helm/actions/workflows/lint.yaml/badge.svg)
[![Artifact Hub](https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/kubesec)](https://artifacthub.io/packages/search?repo=kubesec)

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

## Roadmap

- [ ] Add [pagination support for large clusters](https://kubernetes.io/docs/reference/using-api/api-concepts/#retrieving-large-results-sets-in-chunks) when running on job modes.
- [ ] Add chart coverage *"helm unittest"*.

## Support

You can complement the chart with [the UI from here]() to visualize and analyze reports.

In case the work here, you can share me a cup of coffee ✌️

<a href="https://www.buymeacoffee.com/abarrak" target="_blank">
  <img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" style="height: 50px !important;width: 170px !important;" >
</a>


## License

MIT.
