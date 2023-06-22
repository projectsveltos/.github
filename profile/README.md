# Sveltos: A Kubernetes Add-on Controller that Simplifys Add-on Management

[![Twitter URL](https://img.shields.io/twitter/url/https/twitter.com/projectsveltos.svg?style=social&label=Follow%20%40projectsveltos)](https://twitter.com/projectsveltos)
[![Slack](https://img.shields.io/badge/join%20slack-%23projectsveltos-brighteen)](https://join.slack.com/t/projectsveltos/shared_invite/zt-1hraownbr-W8NTs6LTimxLPB8Erj8Q6Q)

Sveltos Kubernetes add-on controller simplifies the deployment and management of add-ons in hundreds of Kubernetes clusters. With Sveltos, you can easily automate the deployment process and ensure consistency across your cluster environments. Plus, Sveltos provides platform admins with a solution for multi-tenancy, making it even easier to manage permissions for tenant admins.

<p align="center">
  <img alt="Sveltos Kubernetes add-ons management across clusters" src="https://github.com/projectsveltos/sveltos-manager/blob/dev/doc/multi-clusters.png" width="600"/>
 </p>

## Features

* Deploy Kubernetes [add-ons](https://projectsveltos.github.io/sveltos/addons/) across multiple clusters
* ProjectsVeltos has native support for ClusterAPI powered clusters, and can also easily manage any other cluster, such as EKS, GKE, on-prem clusters, etc 
* Support for Helm charts, Kustomize, YAML, [Carvel ytt](https://projectsveltos.github.io/sveltos/ytt_extension/) and [Jsonnet](https://projectsveltos.github.io/sveltos/jsonnet_extension/)
* Configurable deployment strategies
* Automatic rollbacks
* Create [templates](https://projectsveltos.github.io/sveltos/template/) to express add-ons
* Use templates to instantiate add-ons from management cluster values
* [Addon Constraints](https://projectsveltos.github.io/sveltos/addon_constraint/)
* Enforce constraints when deploying add-ons
* Deploy add-ons in response to events
* Define events in [Lua scripts](https://github.com/projectsveltos/sveltos/blob/main/docs/addon_event_deployment.md#event-definition)
* Framework for [cross-cluster configuration](https://projectsveltos.github.io/sveltos/addon_event_deployment/#cross-clusters)

## Other Features
* [Configuration drift detection](https://projectsveltos.github.io/sveltos/configuration_drift/)
* [Dry run](https://projectsveltos.github.io/sveltos/dryrun/)
* [Notifications](https://projectsveltos.github.io/sveltos/notifications)
* Kubernetes [cluster classification](https://projectsveltos.github.io/sveltos/labels_management/)
* [Multi-tenancy](https://projectsveltos.github.io/sveltos/multi-tenancy/)
* [Techsupport](https://projectsveltos.github.io/sveltos/techsupport/)
* [Snapshot and rollback](https://projectsveltos.github.io/sveltos/snapshot/)

![Kubernetes add-on deployment](https://github.com/projectsveltos/sveltos/blob/main/docs/assets/addons_deployment.gif)

![Kubernetes cluster classification](https://github.com/projectsveltos/sveltos/blob/main/docs/assets/classifier.gif)

## Getting Started

* [Install Sveltos](https://projectsveltos.github.io/sveltos/install/)
* [Deploy add-ons](https://projectsveltos.github.io/sveltos/addons/)

## Documentation

* [Full documentation](https://projectsveltos.github.io/sveltos/)
* [Quickstart guide](https://projectsveltos.github.io/sveltos/quick_start/)

## Branching model

We use the git-flow branching model. The base branch is dev. If you are looking for a stable version, please use the main branch or tags labeled as v0.x.x.

## Contributing to Sveltos

We love to hear from our community!

* Report bugs and suggest features
* Write documentation
* Submit code

## Contact

* [Slack](https://projectsveltos.slack.com/)
* [Email](mailto:hello@projectsveltos.io)

## License

Sveltos is licensed under the Apache License, Version 2.0.

If you like Sveltos, please [star](https://github.com/projectsveltos/sveltos-manager) [:star:](https://github.com/projectsveltos/sveltos-manager) the project on GitHub! This will help other people find it and learn more about it.
