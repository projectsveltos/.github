# Sveltos: A Kubernetes Add-on Controller that Simplifys Add-on Management

[![Twitter URL](https://img.shields.io/twitter/url/https/twitter.com/projectsveltos.svg?style=social&label=Follow%20%40projectsveltos)](https://twitter.com/projectsveltos)
[![Slack](https://img.shields.io/badge/join%20slack-%23projectsveltos-brighteen)](https://join.slack.com/t/projectsveltos/shared_invite/zt-1hraownbr-W8NTs6LTimxLPB8Erj8Q6Q)

👋 Welcome to our project! Our [documentation](https://projectsveltos.github.io/sveltos/) can help you get started and provides lots of in-depth information.

## ✨ What is the Projectsveltos?

Sveltos Kubernetes add-on controller simplifies the deployment and management of add-ons across numerous Kubernetes clusters. It offers support for Helm charts, YAMLs, and Kustomize. With Sveltos, automating the add-on deployment process becomes effortless, ensuring consistency throughout your cluster environments. Additionally, Sveltos provides a solution for platform admins to easily manage permissions for tenant admins, thereby facilitating multi-tenancy.

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

## Add-ons deployment

1. from the management cluster, selects one or more `clusters` with a Kubernetes [label selector](https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/#label-selectors);
2. lists which Kubernetes add-ons need to be deployed on such clusters.

![Kubernetes add-on deployment](https://github.com/projectsveltos/sveltos/blob/main/docs/assets/addons_deployment.gif)

## Add-on compliance

 Use OpenAPI or Lua to define configuration add-on compliances. Let Sveltos enforces those.

 ![Event driven framework](https://github.com/projectsveltos/sveltos/raw/main/docs/assets/addon_compliance.gif)

## Event driven framework

Sveltos supports defining an event using Lua. Sveltos can be instructed to deploy add-ons when an event happens in any of the managed cluster.
In this example an event is defined as creation/deletion of a Service instance in certain managed cluster. When an instance of such event happens, Sveltos is instructed to create a NetworkPolicy opening traffic to that service.

![Event driven framework](https://github.com/projectsveltos/demos/blob/main/event-driven/event_driven_framework.gif)

## Event driven framework: cross cluster configuration

With Sveltos' event-driven framework, your add-ons will be automatically deployed to the same cluster where the event is detected, allowing for quick and easy deployment. But that's not all - Sveltos can also be configured for cross-cluster configuration, so you can watch for events in one cluster and deploy add-ons to a set of different clusters. With Sveltos, managing add-ons in Kubernetes has never been easier!

![Event driven framework](https://github.com/projectsveltos/sveltos/raw/main/docs/assets/event_based_cross_cluster.gif)

## Configuration Drift Detection
Sveltos can automatically detect drift detection between the desired state, defined in the management cluster, and actual state of your clusters and recover from it.

![Configuration drift recovery](https://github.com/projectsveltos/demos/blob/main/configuration_drift/reconcile_configuration_drift.gif)

## Cluster classification

Sveltos Classifier is an optional component of the Sveltos project and it is used to dynamically classify a cluster based on its runtime configuration (Kubernetes version, deployed resources and more).

Classifier currently supports the following classification criterias:
1. Kubernetes version
2. Kubernetes resources
   
![Kubernetes cluster classification](https://github.com/projectsveltos/sveltos/blob/main/docs/assets/classifier.gif)

## Getting Started

* [Install Sveltos](https://projectsveltos.github.io/sveltos/install/)
* [Deploy add-ons](https://projectsveltos.github.io/sveltos/addons/)

## Documentation

* [Full documentation](https://projectsveltos.github.io/sveltos/)
* [Quickstart guide](https://projectsveltos.github.io/sveltos/quick_start/)

## Branching model

We use the git-flow branching model. The base branch is dev. If you are looking for a stable version, please use the main branch or tags labeled as v0.x.x.

## 🤗 Contributing to Sveltos

We love to hear from our community!

* Report bugs and suggest features
* Write documentation
* Submit code

## Contact

* <img src="https://github.com/projectsveltos/.github/blob/main/docs/slack_logo.png" alt="Slack" width="25" /> [Slack](https://projectsveltos.slack.com/)
* <img src="https://github.com/projectsveltos/.github/blob/main/docs/email_logo.png" alt="Email" width="25" /> [Email](mailto:hello@projectsveltos.io)

## License

Sveltos is licensed under the Apache License, Version 2.0.

If you like Sveltos, please [star](https://github.com/projectsveltos/addon-controller) [:star:](https://github.com/projectsveltos/addon-controller) the project on GitHub! This will help other people find it and learn more about it.
