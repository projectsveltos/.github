# Sveltos

[![Twitter URL](https://img.shields.io/twitter/url/https/twitter.com/projectsveltos.svg?style=social&label=Follow%20%40projectsveltos)](https://twitter.com/projectsveltos)
[![Slack](https://img.shields.io/badge/join%20slack-%23projectsveltos-brighteen)](https://join.slack.com/t/projectsveltos/shared_invite/zt-1hraownbr-W8NTs6LTimxLPB8Erj8Q6Q)

Full documentation [projectsveltos.io](http://projectsveltos.io/). If you like the project, please leave us a [:star2:](https://github.com/projectsveltos/sveltos-manager) if you haven't done so yet. **Thank you.**

Today, it's very common for organizations to run and manage multiple Kubernetes clusters across different cloud providers or infrastructures. With an increasing number of clusters, consistently managing addons is not an easy task.

Sveltos is a lightweight application designed to manage hundreds of clusters. It does so by providing declarative APIs to deploy Kubernetes addons across multiple clusters. Sveltos focuses not only on the ability to scale the number of clusters it can manage, but also to give visibility to exactly which addons are installed on each cluster.

Sveltos comes with support to automatically discover [ClusterAPI](https://github.com/kubernetes-sigs/cluster-api) powered clusters. Any other cluster (GKE for instance) can easily be registered with Sveltos. Then, Sveltos can manage Kubernetes addons on all the clusters seamless.

![Sveltos in action](https://github.com/projectsveltos/sveltos-manager/blob/dev/doc/multi-clusters.png)

The idea is simple:
1. from the management cluster, selects one or more `clusters` with a Kubernetes [label selector](https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/#label-selectors);
2. lists which Kubernetes addons need to be deployed on such clusters.

## Addons deployment

![Sveltos in action](https://github.com/projectsveltos/sveltos-manager/blob/main/doc/sveltos.png)

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

## Branching model

We use the git-flow branching model. The base branch is dev. If you are looking for a stable version, please use the main branch or tags labeled as v0.x.x.

## Contributing 
❤️ Your contributions are always welcome! If you want to contribute, have questions, noticed any bug or want to get the latest project news, you can connect with us in the following ways:

1. Open a bug/feature enhancement on github [![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](https://github.com/projectsveltos/sveltos-manager/issues)
2. Chat with us on the Slack in the #projectsveltos channel [![Slack](https://img.shields.io/badge/join%20slack-%23projectsveltos-brighteen)](https://join.slack.com/t/projectsveltos/shared_invite/zt-1hraownbr-W8NTs6LTimxLPB8Erj8Q6Q)
3. [Contact Us](mailto:support@projectsveltos.io)

If you like the project, please leave us a [:star2:](https://github.com/projectsveltos/sveltos-manager) if you haven't done so yet. **Thank you.**

