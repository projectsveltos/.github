# Sveltos: A Kubernetes Add-on Controller that Simplifies Add-on Management

[![Twitter URL](https://img.shields.io/twitter/url/https/twitter.com/projectsveltos.svg?style=social&label=Follow%20%40projectsveltos)](https://twitter.com/projectsveltos)
[![Slack](https://img.shields.io/badge/join%20slack-%23projectsveltos-brighteen)](https://join.slack.com/t/projectsveltos/shared_invite/zt-1hraownbr-W8NTs6LTimxLPB8Erj8Q6Q)

👋 Welcome to our project! Our [documentation](https://projectsveltos.github.io/sveltos/) will help you get started and provides an in-depth information about the projects and the features.

## ✨ What is Project Sveltos?

[Sveltos](https://github.com/projectsveltos "Manage Kubernetes add-ons") is a Kubernetes **add-on controller** that simplifies the deployment and management of Kubernetes **add-ons** and **applications** across **multiple** clusters whether on-prem, in the cloud or a multitenant environment.

Sveltos runs in a **management cluster**. It assists users in programmatically deploying and managing Kubernetes add-ons and applications to **any** cluster in the fleet, including the management cluster.

Sveltos supports a variety of add-on formats, including **Helm charts**, raw **YAML/JSON**, **Kustomize**, **Carvel ytt**, and **Jsonnet**.

<p align="center">
  <img alt="Sveltos Kubernetes add-ons management across clusters" src="https://projectsveltos.github.io/sveltos/assets/multi-clusters.png" width="600"/>
</p>

Sveltos motto: **"adding a new cluster with the right labels automatically brings everything to the desired state."**

## Features

* **Observability**: Sveltos offers different endpoints for notifications. The notifications can be used by other tools to perform additional actions or trigger workflows. The supported types are Slack, Teams, Discord, WebEx, and Kubernetes events.
* **Templating**: Patching the rendered resources made easy! Sveltos allows Kubernetes add-ons and applications to be represented as templates. Before deploying to the **managed** clusters, Sveltos instantiates the templates with information gathered from either the **management** or the **managed** clusters. This allows consistent definition across multiple clusters with minimal adjustments and administration overhead.
* **Orchestrated Deployment Order**: The Sveltos CRDs (Custom Resource Definition) are deployed in the exact order they appear in the definition file. That ensures a predictable and controlled deployment order.
* **Multitenancy**: Sveltos was created with the multitenancy concept in mind.Sveltos `ClusterProfile` and `Profile` resources allow platform administrators to facilitate full isolation or tenants sharing a cluster.
* **Events**: `Sveltos Event Framework` allows the deployment of add-ons and applications in response to specific events with the use of the [Lua](https://www.lua.org/) language. That allows dynamic and adaptable deployments based on different needs and use cases.
* [**Managed Services**](https://projectsveltos.github.io/sveltos/events/managed-services/) 

## Why Sveltos?

Sveltos was built to address the challenges posed by various CI/CD tools. Sveltos was designed to complement or even replace existing GitOps tools, and its integration with **Flux CD** significantly enhances the GitOps approach at scale.

Key features of Sveltos include multitenancy, agent-based drift notification and synchronisation, and resource optimisation. These features ensure **secure**, **reliable**, and **stable** deployments of Kubernetes add-ons and applications, while reducing operational costs in both on-prem and cloud environments.

👉 If you find this project useful, consider giving it a [⭐️ star](https://github.com/projectsveltos/addon-controller/stargazers)! Your support helps bring more attention to the project, allowing us to enhance it even further.

## Getting Started

* [Quickstart](https://projectsveltos.github.io/sveltos/getting_started/install/quick_start/)
* [Install Sveltos](https://projectsveltos.github.io/sveltos/getting_started/install/install/)

## Documentation

* [Complete documentation](https://projectsveltos.github.io/sveltos/)

## Dashboard

[![Sveltos Dashboard](https://img.youtube.com/vi/GspTTGAmQwk/0.jpg)](https://www.youtube.com/watch?v=GspTTGAmQwk)


## Adopters

See the list of [organizations](https://github.com/projectsveltos/adopters/blob/main/ADOPTERS.md) currently using Projectsveltos.


🤗 **We encourage contributions!** If your organization uses Projectsveltos, consider adding it to the list. This helps build project momentum and demonstrates the growing community.


## See it in Action

[![Sveltos introduction](https://img.youtube.com/vi/bsWEo79w09c/0.jpg)](https://www.youtube.com/watch?v=bsWEo79w09c)

<p align="center">
   <img alt="Kubernetes add-on deployment" src="https://github.com/projectsveltos/sveltos/blob/main/docs/assets/addons_deployment.gif" width="600"/>
 </p>

<p align="center">
   <img alt="Configuration drift recovery" src="https://github.com/projectsveltos/demos/blob/main/configuration_drift/reconcile_configuration_drift.gif" width="600"/>
 </p>

<p align="center">
   <img alt="External Secrets Operator and Sveltos integration" src="https://github.com/projectsveltos/sveltos/blob/main/docs/assets/external_secret.gif" width="600"/>
 </p>

<p align="center">
   <img alt="DB as a Service" src="https://github.com/projectsveltos/sveltos/blob/main/docs/assets/sveltos-db-as-a-service.gif" width="600"/>
 </p>

## Branching model

We use the git-flow branching model. The base branch is dev. If you are looking for a stable version, please use the main branch or tags labeled as v0.x.x.

## 🤗 Contributing to Sveltos

We love to hear from our community!

* Report bugs and suggest features
* Write documentation
* Submit code

## Contact

* <img src="https://github.com/projectsveltos/.github/blob/main/docs/slack_logo.png" alt="Slack" width="25" /> [Slack](https://join.slack.com/t/projectsveltos/shared_invite/zt-1hraownbr-W8NTs6LTimxLPB8Erj8Q6Q)
* <img src="https://github.com/projectsveltos/.github/blob/main/docs/email_logo.png" alt="Email" width="25" /> [Email](mailto:support@projectsveltos.io)
* <img src="https://github.com/projectsveltos/.github/blob/main/docs/twitter_logo.png" alt="Twitter" width="25" /> [Twitter](https://twitter.com/projectsveltos)

## License

Sveltos is licensed under the Apache License, Version 2.0.

If you like Sveltos, please [star](https://github.com/projectsveltos/addon-controller) [:star:](https://github.com/projectsveltos/addon-controller) the project on GitHub! This will help other people find it and learn more about it.
