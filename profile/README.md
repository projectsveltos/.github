# Sveltos

[![Twitter URL](https://img.shields.io/twitter/url/https/twitter.com/projectsveltos.svg?style=social&label=Follow%20%40projectsveltos)](https://twitter.com/projectsveltos)
[![Slack](https://img.shields.io/badge/join%20slack-%23projectsveltos-brighteen)](https://join.slack.com/t/projectsveltos/shared_invite/zt-1hraownbr-W8NTs6LTimxLPB8Erj8Q6Q)


Hey there! Are you a Kubernetes enthusiast looking for a lightweight application to manage add-ons in hundreds of clusters? Look no further than Sveltos!

Sveltos is a powerful tool that makes managing Kubernetes add-ons a breeze. It automatically discovers [ClusterAPI](https://github.com/kubernetes-sigs/cluster-api) powered clusters and allows you to easily register any other cluster (like GKE). Then, it seamlessly manages Kubernetes add-ons across all your clusters.

But that's not all! Sveltos comes loaded with features like event-driven add-on deployment (using Lua scripts), configuration drift detection, and multi-tenancy to easily manage permissions for tenant admins. You can even preview changes with a dry run and rollback configurations with ease.

And let's not forget about the documentation! Head over to [projectsveltos.io](http://projectsveltos.io/) for the full scoop. And if you love Sveltos as much as we do, show us some love with a [:star:](https://github.com/projectsveltos/sveltos-manager). Your support means a lot to us. **Thank you 🙏.**

## Features List

1. Kubernetes [add-on distribution](https://projectsveltos.github.io/sveltos/addons/) across multiple clusters;
2. [Event driven framework](https://projectsveltos.github.io/sveltos/addon_event_deployment/) to deploy add-ons as response to events in managed clusters. Event can be defined in the form of Lua script. Add-ons can be expressed as template and instantiated using information from resources in the managed clusters;
2. [Configuration drift detection](https://projectsveltos.github.io/sveltos/configuration_drift/);
3. [Notification](https://projectsveltos.github.io/sveltos/notifications): Sveltos can be configured to send notifications (Kubernetes event and Slack, Webex messages) when for instance all add-ons are deployed in a cluster;
4. [Templates](https://projectsveltos.github.io/sveltos/template/) instantiated reading values from management cluster;
5. [Multi-tenancy](https://projectsveltos.github.io/sveltos/multi-tenancy/) allowing platform admin to easily grant permissions to tenant admins and have Sveltos enforces those;
6. [Dry run](https://projectsveltos.github.io/sveltos/configuration/#dryrun-mode) to preview effect of a change;
7. Kubernetes [cluster classification](https://projectsveltos.github.io/sveltos/labels_management/) and automatic label management based on cluster runtime states;
8. [Techsupport](https://projectsveltos.github.io/sveltos/techsupport/): collect tech support from managed clusters;
9. Configuration [snapshots and rollback](https://projectsveltos.github.io/sveltos/snapshot/).

![Sveltos in action](https://github.com/projectsveltos/sveltos-manager/blob/dev/doc/multi-clusters.png)


## Add-ons deployment

The idea is simple:
1. from the management cluster, selects one or more `clusters` with a Kubernetes [label selector](https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/#label-selectors);
2. lists which Kubernetes add-ons need to be deployed on such clusters.

![Sveltos in action](https://github.com/projectsveltos/sveltos-manager/blob/main/doc/sveltos.png)

## Template

Values can be passed to helm charts. Sveltos can also fetch needed values from Kubernetes instances present in the management cluster.
For instance following ClusterProfile is reading pod CIDRs from CAPI Cluster instance.

<img src="https://raw.githubusercontent.com/projectsveltos/.github/main/docs/sveltos_calico.png" width="500">

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

![Sveltos Classifier in action](https://github.com/projectsveltos/demos/blob/main/classifier/classifier.gif)

## Multi-tenancy

Sveltos provides platform admin with an easy way to grant permissions to tenant admins. Tenant admins can then use Sveltos to deploy tenant applications.

![Sveltos Classifier in action](https://github.com/projectsveltos/demos/blob/main/multi-tenancy/multi_tenancy.gif)

## Branching model

We use the git-flow branching model. The base branch is dev. If you are looking for a stable version, please use the main branch or tags labeled as v0.x.x.

## Contributing to Sveltos

🎉 We welcome and appreciate all contributions to Sveltos! Whether you want to report a bug, suggest a new feature, or simply ask a question, we'd love to hear from you. Here are a few ways to connect with us:

1. Open a bug/feature enhancement on github [![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](https://github.com/projectsveltos/sveltos-manager/issues)
2. Chat with us on the Slack in the #projectsveltos channel [![Slack](https://img.shields.io/badge/join%20slack-%23projectsveltos-brighteen)](https://join.slack.com/t/projectsveltos/shared_invite/zt-1hraownbr-W8NTs6LTimxLPB8Erj8Q6Q)
3. [Contact Us](mailto:support@projectsveltos.io)

## 👏 Support this project

If you like the project, please [give us a](https://github.com/projectsveltos/sveltos-manager) [:star:](https://github.com/projectsveltos/sveltos-manager) if you haven't done so yet. Your support means a lot to us. **Thank you :pray:.**

