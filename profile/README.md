# Sveltos: Kubernetes Add-on Controller for Multi-Cluster Fleets

[![LinkedIn](https://custom-icon-badges.demolab.com/badge/LinkedIn-0A66C2?logo=linkedin-white&logoColor=fff)](https://www.linkedin.com/company/projectsveltos/)
[![Slack](https://img.shields.io/badge/join%20slack-%23projectsveltos-brighteen)](https://join.slack.com/t/projectsveltos/shared_invite/zt-1hraownbr-W8NTs6LTimxLPB8Erj8Q6Q)
[![X URL](https://img.shields.io/twitter/url/https/twitter.com/projectsveltos.svg?style=social&label=Follow%20%40projectsveltos)](https://x.com/projectsveltos)

👋 Welcome to **Projectsveltos**!

<div align="center">

| 🌐 Website | 📚 Documentation | 🏢 Adopters | 📅 Book a Demo | 💼 Enterprise Support |
|:---:|:---:|:---:|:---:|:---:|
| [Visit](https://website.projectsveltos.io) | [Get Started](https://projectsveltos.io/latest/) | [View List](https://website.projectsveltos.io/companies/) |[Schedule 30 min](https://cal.com/gianluca-mardente-nuclsu/30min) | [Contact Us](mailto:gianluca@projectsveltos.io) |

</div>

## ✨ What is Project Sveltos?

[Sveltos](https://github.com/projectsveltos "Manage Kubernetes add-ons") is a [Kubernetes add-on controller](https://github.com/projectsveltos/addon-controller). It deploys and manages add-ons and applications across many clusters using label-based matching. Sveltos does not compete with GitOps controllers like **ArgoCD** or **Flux**. Instead, it extends their capabilities. It runs in a **management cluster** and supports **Helm charts**, raw **YAML/JSON**, **Kustomize**, **Carvel ytt**, and **Jsonnet** formats.

Sveltos stands out for:

- **Label-based fleet targeting**: One configuration serves any matching cluster.
- **Flexible drift detection (agent or agentless)**: Choose the mode that fits your environment.
- **Per-cluster templating**: Same definition, different values per cluster.
- **Event framework and progressive rollouts**: Safe, automated, and adaptable.
- **Edge Deployments**: Lightweight agents built for tight CPU, memory, and bandwidth budgets. Sveltos deploys only what's needed.

> **"Adding a new cluster with the right labels automatically brings everything to the desired state."**

<p align="center">
  <img alt="Sveltos Kubernetes add-ons management across clusters" src="https://raw.githubusercontent.com/projectsveltos/sveltos/refs/heads/main/docs/assets/sveltos_pull_mode_readme.png" width="600"/>
</p>

> [!TIP]
> If you find this project useful, please give it a [⭐️ star](https://github.com/projectsveltos/addon-controller/stargazers) — it helps more people discover Sveltos!

## Features

* **🔄 Orchestrated Deployment Order**: Deploy resources in a defined order using simple Custom Resource Definitions (CRDs). Predictable, controlled rollouts.
* **👥 Multitenancy**: Use `ClusterProfile` for fleet-wide policies and `Profile` for namespace-scoped tenant isolation.
* **🧩 Templating**: Define add-ons and applications as templates; Sveltos instantiates them per cluster using cluster metadata.
* **⚡ Event-driven Framework**: [Trigger deployments](https://projectsveltos.github.io/sveltos/events/managed-services/) from in-cluster or NATS events, with matching logic written in [Lua](https://www.lua.org/) or [CEL](https://cel.dev/).
* **🛡️ Pull Mode**: Deploy into restricted environments: air-gapped, edge, or behind firewalls.
* **🚦 Progressive rollouts**: Phased deployments from a single configuration; no need to maintain multiple profiles.
* **📢 Observability**: Notifications via Slack, Teams, Discord, Webex, Telegram, SMTP, or Kubernetes events.

## See it in Action

### Deploy add-ons across clusters

<p align="center">
   <img alt="Kubernetes add-on deployment" src="https://github.com/projectsveltos/sveltos/blob/main/docs/assets/addons_deployment.gif" width="600"/>
</p>

### Recover from configuration drift

<p align="center">
   <img alt="Configuration drift recovery" src="https://github.com/projectsveltos/demos/blob/main/configuration_drift/reconcile_configuration_drift.gif" width="600"/>
</p>

### Explore the Sveltos dashboard

[![Sveltos Dashboard](https://img.youtube.com/vi/FjFtvrG8LWQ/0.jpg)](https://www.youtube.com/watch?v=FjFtvrG8LWQ)

## Contact and community

* <img src="https://github.com/projectsveltos/.github/blob/main/docs/slack_logo.png" alt="Slack" width="25" /> [Slack](https://join.slack.com/t/projectsveltos/shared_invite/zt-1hraownbr-W8NTs6LTimxLPB8Erj8Q6Q)
* <img src="https://github.com/projectsveltos/.github/blob/main/docs/email_logo.png" alt="Email" width="25" /> [Email](mailto:gianluca@projectsveltos.io)
* <img src="https://github.com/projectsveltos/.github/blob/main/docs/linkedin_logo.png" alt="Linkedin" width="25" /> [LinkedIn](https://www.linkedin.com/company/projectsveltos/)
* <img src="https://github.com/projectsveltos/.github/blob/main/docs/twitter_logo.png" alt="X" width="25" /> [X](https://x.com/projectsveltos)

Contributions are always welcome — report bugs, improve docs, or submit code via [GitHub Issues](https://github.com/projectsveltos/sveltos-manager/issues).

## License

Sveltos is licensed under the Apache License, Version 2.0.
