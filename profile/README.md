# Sveltos

[![Twitter URL](https://img.shields.io/twitter/url/https/twitter.com/projectsveltos.svg?style=social&label=Follow%20%40projectsveltos)](https://twitter.com/projectsveltos)
[![Slack](https://img.shields.io/badge/join%20slack-%23projectsveltos-brighteen)](https://join.slack.com/t/projectsveltos/shared_invite/zt-1hraownbr-W8NTs6LTimxLPB8Erj8Q6Q)

Full documentation [projectsveltos.io](http://projectsveltos.io/).

If you like the project, please [give us a](https://github.com/projectsveltos/sveltos-manager) [:star:](https://github.com/projectsveltos/sveltos-manager) if you haven't done so yet. Your support means a lot to us. **Thank you 🙏.**

Sveltos is a lightweight application designed to manage Kubernetes add-ons in hundreds of clusters. 

Sveltos comes with support to automatically discover [ClusterAPI](https://github.com/kubernetes-sigs/cluster-api) powered clusters. Any other cluster (GKE for instance) can easily be registered with Sveltos. Then, Sveltos can manage Kubernetes add-ons on all the clusters seamlessly.

## Features List

1. Kubernetes [add-on distribution](https://projectsveltos.github.io/sveltos/addons/) across multiple clusters;
2. [Configuration drift detection](https://projectsveltos.github.io/sveltos/configuration_drift/);
3. [Notification](https://github.com/projectsveltos/sveltos/blob/main/docs/notifications.md): Sveltos can be configured to send notifications (Kubernetes event and Slack messages) when for instance all add-ons are deployed in a cluster;
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

## Contributing
❤️ Your contributions are always welcome! If you want to contribute, have questions, noticed any bug or want to get the latest project news, you can connect with us in the following ways:

1. Open a bug/feature enhancement on github [![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](https://github.com/projectsveltos/sveltos-manager/issues)
2. Chat with us on the Slack in the #projectsveltos channel [![Slack](https://img.shields.io/badge/join%20slack-%23projectsveltos-brighteen)](https://join.slack.com/t/projectsveltos/shared_invite/zt-1hraownbr-W8NTs6LTimxLPB8Erj8Q6Q)
3. [Contact Us](mailto:support@projectsveltos.io)

## 👏 Support this project

If you like the project, please [give us a](https://github.com/projectsveltos/sveltos-manager) [:star:](https://github.com/projectsveltos/sveltos-manager) if you haven't done so yet. Your support means a lot to us. **Thank you :pray:.**

