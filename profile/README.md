# Sveltos

[![Twitter Follow](https://img.shields.io/twitter/follow/projectsveltos?style=social)](https://twitter.com/projectsveltos)
[![Slack](https://img.shields.io/badge/join%20slack-%23projectsveltos-brighteen)](https://join.slack.com/t/projectsveltos/shared_invite/zt-1hraownbr-W8NTs6LTimxLPB8Erj8Q6Q)

Full documentation [projectsveltos.io](projectsveltos.io).

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

## Cluster classification

Sveltos Classifier is an optional component of the Sveltos project and it is used to dynamically classify a cluster based on its runtime configuration (Kubernetes version, deployed resources and more).

Classifier currently supports the following classification criterias:
1. Kubernetes version
2. Kubernetes resources

![Sveltos Classifier in action](https://github.com/projectsveltos/demos/blob/main/classifier/classifier.gif)

If you like the project, please leave us a [⭐](https://github.com/projectsveltos/sveltos-manager) if you haven't done so yet. Thank you.

## Branching model

We use the git-flow branching model. The base branch is dev. If you are looking for a stable version, please use the main branch or tags labeled as v0.x.x.
