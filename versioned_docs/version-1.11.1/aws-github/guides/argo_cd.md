---
sidebar_position: 2
---

# Argo CD

Argo CD is a GitOps continuous delivery tool for Kubernetes. We use it to manage all of our applications across our Kubernetes clusters.

Argo CD is really great at providing a straightforward mechanism for you to manage Helm charts, their versions, their configuration overrides, and whether their state is in sync with what is running on your clusters.

![argcd apps](/img/argocd-apps.png)

## Managing applications in Argo CD

The configuration for all of your apps in your kubernetes cluster can be found in your new gitops repository at path ```/registry```.

GitHub registry applications:

![gitops registry](/img/gitops-registry.png)

Each of these yaml files will include details regarding the application's source, destination, and Helm configuration overrides.

## Applying changes in Argo CD

Once you change the desired state of the app in the gitops repository main branch, the registered app-of-apps will sync, and any apps in kubernetes that need adjustment will automatically sync with the state that's in git.

## Adding applications to Argo CD

The registry of our Argo CD apps are all in the ```/registry``` root directory. Any application added here will be added to Argo CD. An app can also be an app-of-apps if you require multiple components to be delivered as a suite. You'll see plenty of examples to follow in the ```/registry``` directory.

## External docs

https://argoproj.github.io/argo-cd/