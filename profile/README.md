# Sveltos: A Kubernetes Add-on Controller that Simplifies Add-on Management

[![Twitter URL](https://img.shields.io/twitter/url/https/twitter.com/projectsveltos.svg?style=social&label=Follow%20%40projectsveltos)](https://twitter.com/projectsveltos)
[![Slack](https://img.shields.io/badge/join%20slack-%23projectsveltos-brighteen)](https://join.slack.com/t/projectsveltos/shared_invite/zt-1hraownbr-W8NTs6LTimxLPB8Erj8Q6Q)

👋 Welcome to our project! Our [documentation](https://projectsveltos.github.io/sveltos/) can help you get started and provides lots of in-depth information.

## ✨ What is Project Sveltos?

Sveltos is a Kubernetes add-on controller that simplifies the deployment and management of add-ons and applications across multiple clusters. It runs in the management cluster and can programmatically deploy and manage add-ons and applications on any cluster in the fleet, including the management cluster itself. Sveltos supports a variety of add-on formats, including Helm charts, raw YAML, Kustomize, Carvel ytt, and Jsonnet.

<p align="center">
  <img alt="Sveltos Kubernetes add-ons management across clusters" src="https://projectsveltos.github.io/sveltos/assets/multi-clusters.png" width="600"/>
 </p>

Sveltos allows you to represent add-ons and applications as templates. Before deploying to managed clusters, Sveltos instantiates these templates. Sveltos can gather the information required to instantiate the templates from either the management cluster or the managed clusters themselves.

This enables you to use the same add-on configuration across all of your clusters, while still allowing for some variation, such as different add-on configuration values. In other words, Sveltos lets you define add-ons and applications in a reusable way. You can then deploy these definitions to multiple clusters, with minor adjustments as needed. This can save you a lot of time and effort, especially if you manage a large number of clusters.

Sveltos also has an event-driven framework that allows you to deploy add-ons and applications in an orderly manner, or to deploy add-ons in response to certain events.

With its sharding strategy, Sveltos can manage hundreds of managed clusters and applications by distributing the load across multiple instances of Sveltos controllers. To achieve this, add the annotation sharding.projectsveltos.io/key to managed clusters.

<p align="center">
  <img alt="Sveltos sharding" src="https://github.com/projectsveltos/sveltos/blob/main/docs/assets/sharding.gif" width="600"/>
 </p>


If you like Sveltos, please [star](https://github.com/projectsveltos/addon-controller) [:star:](https://github.com/projectsveltos/addon-controller) the project on GitHub! This will help other people find it and learn more about it.

## Features

* Deploy and manage Kubernetes [add-ons](https://projectsveltos.github.io/sveltos/addons/addons/) across multiple clusters;
* Native support for ClusterAPI powered clusters, and can also easily manage any other cluster, such as EKS, GKE, on-prem clusters, etc;
* Support for Helm charts, Kustomize, YAML, [Carvel ytt](https://projectsveltos.github.io/sveltos/template/ytt_extension/) and [Jsonnet](https://projectsveltos.github.io/sveltos/template/jsonnet_extension/);
* Addons can be represented as [templates](https://projectsveltos.github.io/sveltos/template/template/) and instantiated using values from management cluster resources. Sveltos can fetch any resource in the management cluster provided that the appropriate RBAC permissions are granted;
* Configurable deployment strategies;
* [Addon Compliance](https://projectsveltos.github.io/sveltos/addon_compliance/): OpenAPI and Lua can be utilized to define custom add-on compliance policies. When deploying add-ons with Sveltos, these policies will be enforced by Sveltos to ensure compliance;
* [Event driven framework](https://projectsveltos.github.io/sveltos/events/addon_event_deployment/) to deploy add-ons as response to events in managed clusters. Events can be defined via Lua scripts;
* Sveltos' event driven framework can also be [cross-cluster configured](https://projectsveltos.github.io/sveltos/events/cross_cluster_configuration/);
* Automatic [rolling upgrade](https://projectsveltos.github.io/sveltos/rolling_upgrade/) for Deployments, StatefulSets, and DaemonSets;
* [Deploy Kubernetes Resources in a Controlled and Orderly Manner](https://projectsveltos.github.io/sveltos/deployment_order/manifest_order/)

## Other Features

* [Configuration drift detection](https://projectsveltos.github.io/sveltos/configuration_drift/);
* [Dry run](https://projectsveltos.github.io/sveltos/dryrun/) to preview effects of a change;
* [Notifications](https://projectsveltos.github.io/sveltos/observability/notifications/): Sveltos can be configured to send notifications (Kubernetes event and Slack, Webex messages) when, for instance, all add-ons are deployed in a cluster;
* Kubernetes [cluster classification](https://projectsveltos.github.io/sveltos/labels_management/): Sveltos can classify a cluster based on its runtime state;
* [Multi-tenancy](https://projectsveltos.github.io/sveltos/multi-tenancy/): platform admins can easily grant permissions to tenant admins and have Sveltos enforce those;
* [Techsupport]([https://projectsveltos.github.io/sveltos/techsupport/](https://projectsveltos.github.io/sveltos/sveltosctl/techsupport/)): collect tech support from managed clusters;
* [Snapshot and rollback](https://projectsveltos.github.io/sveltos/sveltosctl/snapshot/): freeze your policy configurations in time, compare changes between snapshots, and roll back or forward to any saved snapshot.
* Sveltos can gather information from all or subsets of the clusters it manages. This information can then be accessed and displayed using [Sveltos' CLI](https://projectsveltos.github.io/sveltos/observability/show_resources/) in the management cluster.

## Add-ons deployment

1. from the management cluster, selects one or more `clusters` with a Kubernetes [label selector](https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/#label-selectors);
2. lists which Kubernetes add-ons need to be deployed on such clusters.

![Kubernetes add-on deployment](https://github.com/projectsveltos/sveltos/blob/main/docs/assets/addons_deployment.gif)

## Add-on compliance

Use OpenAPI or Lua to define configuration add-on compliance. Let Sveltos enforce them.

![Event driven framework](https://github.com/projectsveltos/sveltos/raw/main/docs/assets/addon_compliance.gif)

## Event driven framework

Sveltos supports defining an event using Lua. An event is a notification that is sent when a certain condition is met. For example, you could create an event that is sent when the PostgreSQL deployment becomes healthy. Events can then be used to trigger the deployment of other resources. For example, you could configure Sveltos to deploy the Job that creates the table in the database when it receives an event that the PostgreSQL deployment is healthy.
In this example Sveltos has been instructed to:

1️⃣ Deploy postgresql deployment and service\
2️⃣ Wait for postgresql deployment to be ready\
3️⃣ Deploy a Job that creates a table in the DB\
4️⃣ Wait for Job to be completed\
5️⃣ Deploy todo-app which can access PostgreSQL deployment\
6️⃣ Wait for todo-app to be healthy\
7️⃣ Deploy a Job that adds an entry to database via todo-app

![Event driven framework](https://github.com/projectsveltos/sveltos/raw/main/docs/assets/sveltos_resource_order.gif)

## Event driven framework: cross cluster configuration

With Sveltos' event-driven framework, your add-ons will be automatically deployed to the same cluster where the event is detected, allowing for quick and easy deployment. But that's not all - Sveltos can also be configured cross-cluster, so you can watch for events in one cluster and deploy add-ons to a set of different clusters. With Sveltos, managing add-ons in Kubernetes has never been easier!

![Event driven framework](https://github.com/projectsveltos/sveltos/raw/main/docs/assets/event_based_cross_cluster.gif)

## Coordinate with Crossplane and other open source projects

Sveltos can also create resources in the management cluster itself. This allows Sveltos to coordinate with other open source projects
before deploying add-ons in the managed cluster.

![ClusterAPI, Sveltos and Crossplane](https://github.com/projectsveltos/sveltos/raw/main/docs/assets/sveltos_clusterapi_crossplane.gif)

## Configuration Drift Detection

Sveltos can automatically detect drift between the desired state, defined in the management cluster, and actual state of your clusters and recover from it.

![Configuration drift recovery](https://github.com/projectsveltos/demos/blob/main/configuration_drift/reconcile_configuration_drift.gif)

## Automatic Rolling Upgrades

Sveltos has the capability to monitor changes within ConfigMap and Secret resources and facilitate rolling upgrades for Deployments, StatefulSets, and DaemonSets. This functionality can be activated by simply setting the reloader field to true in the ClusterProfile.

![Projectsveltos: Rolling Upgrades](https://github.com/projectsveltos/sveltos/blob/main/docs/assets/rolling_upgrades.gif)

## Cluster classification

Sveltos Classifier is an optional component used to dynamically classify a cluster based on its runtime configuration (Kubernetes version, deployed resources, and more).

Classifier currently supports the following criteria:

1. Kubernetes version
2. Kubernetes resources

![Kubernetes cluster classification](https://github.com/projectsveltos/sveltos/blob/main/docs/assets/classifier.gif)

## Observability
Sveltos can monitor the healths of resources in managed clusters and send notifications when something happens. For instance detect Pod instances in crashloopbackoff and send a Slack notification.

![Detect Pods in crashloopbackoff](https://github.com/projectsveltos/sveltos/blob/main/docs/assets/notification.gif)


## Visualize managed cluster resources from central location

Sveltos now offers the ability to gather information from all or subsets of the clusters it manages. This information can then be accessed and displayed using Sveltos' CLI in the management cluster.

![Sveltosctl show resources](https://github.com/projectsveltos/sveltos/blob/main/docs/assets/show_resources.png)

## External Secret Management

The integration of External Secret Operator and Sveltos provides a powerful solution for secret management. External Secret Operator fetches secrets from external APIs and creates Kubernetes secrets, while Sveltos efficiently distributes these fetched secrets to the managed clusters. In case of any changes to the secrets in the external API, External Secret Operator updates the secrets in the management cluster, and Sveltos ensures the reconciliation of state in each managed cluster where the secret was distributed.

![External Secrets Operator and Sveltos integration](https://github.com/projectsveltos/sveltos/blob/main/docs/assets/external_secret.gif)

## Getting Started

* [Install Sveltos](https://projectsveltos.github.io/sveltos/install/install/)
* [Quickstart](https://projectsveltos.github.io/sveltos/install/quick_start/) for trying out Projectsveltos with a test cluster

## Documentation

* [Complete documentation](https://projectsveltos.github.io/sveltos/)

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
