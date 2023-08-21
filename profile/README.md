# Sveltos: A Kubernetes Add-on Controller that Simplifys Add-on Management

[![Twitter URL](https://img.shields.io/twitter/url/https/twitter.com/projectsveltos.svg?style=social&label=Follow%20%40projectsveltos)](https://twitter.com/projectsveltos)
[![Slack](https://img.shields.io/badge/join%20slack-%23projectsveltos-brighteen)](https://join.slack.com/t/projectsveltos/shared_invite/zt-1hraownbr-W8NTs6LTimxLPB8Erj8Q6Q)

👋 Welcome to our project! Our [documentation](https://projectsveltos.github.io/sveltos/) can help you get started and provides lots of in-depth information.

## ✨ What is the Projectsveltos?

Sveltos Kubernetes add-on controller simplifies the deployment and management of add-ons and applications across numerous Kubernetes clusters. It offers support for Helm charts, YAMLs, and Kustomize. With Sveltos, automating the add-on deployment process becomes effortless, ensuring consistency throughout your cluster environments. Additionally, Sveltos provides a solution for platform admins to easily manage permissions for tenant admins, thereby facilitating multi-tenancy.

<p align="center">
  <img alt="Sveltos Kubernetes add-ons management across clusters" src="https://github.com/projectsveltos/sveltos-manager/blob/dev/doc/multi-clusters.png" width="600"/>
 </p>

## Features

* Deploy and manage Kubernetes [add-ons](https://projectsveltos.github.io/sveltos/addons/) across multiple clusters; 
* Projectsveltos has native support for ClusterAPI powered clusters, and can also easily manage any other cluster, such as EKS, GKE, on-prem clusters, etc;
* Support for Helm charts, Kustomize, YAML, [Carvel ytt](https://projectsveltos.github.io/sveltos/ytt_extension/) and [Jsonnet](https://projectsveltos.github.io/sveltos/jsonnet_extension/);
* Addons can be represented as [templates](https://projectsveltos.github.io/sveltos/template/) and instantiated using values from management cluster resources. Sveltos can fetch any resource in the management cluster provided that the appropriate RBAC permissions are granted;
* Configurable deployment strategies;
* [Addon Compliance](https://projectsveltos.github.io/sveltos/addon_compliance/): OpenAPI and Lua can be utilized to define custom add-on compliance policies. When deploying add-ons with Sveltos, these policies will be enforced by Sveltos to ensure compliance;
* [Event driven framework](https://projectsveltos.github.io/sveltos/addon_event_deployment/) to deploy add-ons as response to events in managed clusters. Event can be defined in the form of Lua script;
* Sveltos' event driven framework can also be configured for [cross-cluster configuration];(https://projectsveltos.github.io/sveltos/addon_event_deployment/#cross-clusters);
* Automatic [rolling upgrade](https://projectsveltos.github.io/sveltos/rolling_upgrade/) for Deployments, StatefulSets and DaemonSet;
* [Deploy Kubernetes Resources in a Controlled and Orderly Manner](https://projectsveltos.github.io/sveltos/manifest_order) 
  
## Other Features
* [Configuration drift detection](https://projectsveltos.github.io/sveltos/configuration_drift/);
* [Dry run](https://projectsveltos.github.io/sveltos/dryrun/) to preview effect of a change;
* [Notifications](https://projectsveltos.github.io/sveltos/notifications): Sveltos can be configured to send notifications (Kubernetes event and Slack, Webex messages) when for instance all add-ons are deployed in a cluster;
* Kubernetes [cluster classification](https://projectsveltos.github.io/sveltos/labels_management/): Sveltos can classify a cluster based on its runtime state;
* [Multi-tenancy](https://projectsveltos.github.io/sveltos/multi-tenancy/): platform admin can easily grant permissions to tenant admins and have Sveltos enforces those;
* [Techsupport](https://projectsveltos.github.io/sveltos/techsupport/): collect tech support from managed clusters;
* [Snapshot and rollback](https://projectsveltos.github.io/sveltos/snapshot/): freeze your policy configurations in time, compare changes between snapshots, and roll back or forward to any saved snapshot.
* Sveltos can gather information from all or subsets of the clusters it manages. This information can then be accessed and displayed using [Sveltos' CLI](https://projectsveltos.github.io/sveltos/show_resources/) in the management cluster.

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

## Visualize managed cluster resources from central location

Sveltos now offers the ability to gather information from all or subsets of the clusters it manages. This information can then be accessed and displayed using Sveltos' CLI in the management cluster.

![Sveltosctl show resources](https://github.com/projectsveltos/sveltos/blob/main/docs/assets/show_resources.png)

## External Secret Management

The integration of External Secret Operator and Sveltos provides a powerful solution for secret management. External Secret Operator fetches secrets from external APIs and creates Kubernetes secrets, while Sveltos efficiently distributes these fetched secrets to the managed clusters. In case of any changes to the secrets in the external API, External Secret Operator updates the secrets in the management cluster, and Sveltos ensures the reconciliation of state in each managed cluster where the secret was distributed.

![External Secrets Operator and Sveltos integration](https://github.com/projectsveltos/sveltos/blob/main/docs/assets/external_secret.gif)

## Automatic Rolling Upgrades

Sveltos has the capability to monitor changes within ConfigMap and Secret resources and facilitate rolling upgrades for Deployments, StatefulSets, and DaemonSets. This functionality can be activated by simply setting the reloader field to true in the ClusterProfile.

![Projectsveltos: Rolling Upgrades](https://github.com/projectsveltos/sveltos/blob/main/docs/assets/rolling_upgrades.gif)

## Getting Started

* [Install Sveltos](https://projectsveltos.github.io/sveltos/install/)
* [Deploy add-ons](https://projectsveltos.github.io/sveltos/addons/)

## Documentation

* [Complete documentation](https://projectsveltos.github.io/sveltos/)
* [Quickstart](https://projectsveltos.github.io/sveltos/quick_start/) for trying out Projectsveltos with a test cluster
* [Concrete examples](https://projectsveltos.github.io/sveltos/quick_start/) for understanding how Projectsveltos works

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
* <img src="https://github.com/projectsveltos/.github/blob/main/docs/twitter_logo.png" alt="Twitter" width="25" /> [Twitter](https://twitter.com/projectsveltos)

## License

Sveltos is licensed under the Apache License, Version 2.0.

If you like Sveltos, please [star](https://github.com/projectsveltos/addon-controller) [:star:](https://github.com/projectsveltos/addon-controller) the project on GitHub! This will help other people find it and learn more about it.
