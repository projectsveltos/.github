# Sveltos

<img src="https://raw.githubusercontent.com/projectsveltos/.github/main/logos/logo.png" width="200">

Sveltos provides declarative APIs allowing you to deploy Kubernetes addons across multiple Kubernetes clusters.

The idea is simple:
1. from the management cluster, selects one or more `clusters` with a Kubernetes [label selector](https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/#label-selectors);
2. lists which `features` need to be deployed on such clusters.

where term:
1. `clusters` represents [CAPI cluster](https://github.com/kubernetes-sigs/cluster-api/blob/main/api/v1beta1/cluster_types.go);
2. `features` represents either an [helm release](https://helm.sh) or a Kubernetes resource.

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

