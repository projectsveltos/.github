# Sveltos: A Kubernetes Add-on Controller that Simplifies Add-on Management

[![LinkedIn](https://custom-icon-badges.demolab.com/badge/LinkedIn-0A66C2?logo=linkedin-white&logoColor=fff)](https://www.linkedin.com/company/projectsveltos/)
[![Slack](https://img.shields.io/badge/join%20slack-%23projectsveltos-brighteen)](https://join.slack.com/t/projectsveltos/shared_invite/zt-1hraownbr-W8NTs6LTimxLPB8Erj8Q6Q)
[![X URL](https://img.shields.io/twitter/url/https/twitter.com/projectsveltos.svg?style=social&label=Follow%20%40projectsveltos)](https://x.com/projectsveltos)

👋 Welcome to **Projectsveltos**!

<div align="center">

| 🌐 Website | 📚 Documentation | 📅 Book a Demo | 💼 Enterprise Support | 🏢 Adopters |
|:---:|:---:|:---:|:---:|:---:|
| [Visit](https://website.projectsveltos.io) | [Get Started](https://projectsveltos.github.io/sveltos/) | [Schedule 30 min](https://cal.com/gianluca-mardente-nuclsu/30min) | [Contact Us](mailto:gianluca@projectsveltos.io) | [View List](https://github.com/projectsveltos/adopters/blob/main/ADOPTERS.md) |

</div>

## ✨ What is Project Sveltos?

[Sveltos](https://github.com/projectsveltos "Manage Kubernetes add-ons") is a Kubernetes **add-on controller** that simplifies the deployment and management of add-ons and applications across **multiple** clusters — on-prem, cloud, or multitenant. It runs in a **management cluster** and supports **Helm charts**, raw **YAML/JSON**, **Kustomize**, **Carvel ytt**, and **Jsonnet**.

Sveltos integrates seamlessly with **Flux CD** to enhance GitOps at scale. Key strengths include multitenancy, agent-based drift detection and synchronisation, and event-driven deployments via the [Lua](https://www.lua.org/)-based **Event Framework**.

> **"Adding a new cluster with the right labels automatically brings everything to the desired state."**

<p align="center">
  <img alt="Sveltos Kubernetes add-ons management across clusters" src="https://projectsveltos.github.io/sveltos/assets/multi-clusters.png" width="600"/>
</p>

> [!TIP]
> If you find this project useful, please give it a [⭐️ star](https://github.com/projectsveltos/addon-controller/stargazers) — it helps more people discover Sveltos!

## Features

* **Templating**: Deploy add-ons as templates, instantiated with data from the management or managed clusters — consistent config across all clusters with minimal overhead.
* **Orchestrated Deployment Order**: Add-ons deploy in the exact order defined, with support for cross-profile dependencies.
* **Multitenancy**: `ClusterProfile` and `Profile` resources give platform admins global control and tenant admins namespace-scoped isolation.
* **Observability**: Notifications via Slack, Teams, Discord, WebEx, and Kubernetes events.
* **Events**: Deploy add-ons in response to specific cluster events using the [Event Framework](https://projectsveltos.github.io/sveltos/events/managed-services/).

## See it in Action

<p align="center">
   <img alt="Kubernetes add-on deployment" src="https://github.com/projectsveltos/sveltos/blob/main/docs/assets/addons_deployment.gif" width="600"/>
</p>

<p align="center">
   <img alt="Configuration drift recovery" src="https://github.com/projectsveltos/demos/blob/main/configuration_drift/reconcile_configuration_drift.gif" width="600"/>
</p>

[![Sveltos Dashboard](https://img.youtube.com/vi/FjFtvrG8LWQ/0.jpg)](https://www.youtube.com/watch?v=FjFtvrG8LWQ)

## Contact and community

* <img src="https://github.com/projectsveltos/.github/blob/main/docs/slack_logo.png" alt="Slack" width="25" /> [Slack](https://join.slack.com/t/projectsveltos/shared_invite/zt-1hraownbr-W8NTs6LTimxLPB8Erj8Q6Q)
* <img src="https://github.com/projectsveltos/.github/blob/main/docs/email_logo.png" alt="Email" width="25" /> [Email](mailto:gianluca@projectsveltos.io)
* <img src="https://github.com/projectsveltos/.github/blob/main/docs/twitter_logo.png" alt="X" width="25" /> [X](https://x.com/projectsveltos)
* <img src="https://github.com/projectsveltos/.github/blob/main/docs/linkedin_logo.png" alt="Linkedin" width="25" /> [LinkedIn](https://www.linkedin.com/company/projectsveltos/)

Contributions are always welcome — report bugs, improve docs, or submit code via [GitHub Issues](https://github.com/projectsveltos/sveltos-manager/issues).

## License

Sveltos is licensed under the Apache License, Version 2.0.
