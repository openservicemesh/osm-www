---
title: "Announcing OSM v1.0.0"
slug: "announcing-osm-v1"
authorname: "Phillip Gibson & Jon Huhn"
author: "@openservicemesh"
authorlink: "https://twitter.com/openservicemesh"
date: "2022-02-01T08:00:00-15:00"
---

OSM's contributors have been hard at work over the past several months preparing for the v1.0.0 release. Today, the OSM team proudly announces the release of version 1.0.0. Thanks to the community for helping drive the features they want to see in a service mesh and heightening the expectation for OSM to provide enterprise features and functionality.

Reaching a project’s v1.0.0 milestone is a major accomplishment that is also met with a lot of reflection. OSM has come a long way from its initial announcement, and the team continues to focus on the key and necessary features the community needs. We remain committed to OSM’s initial charter, which is to provide a simplified operational experience that doesn’t overburden operators.

While the primary focus has been on testing, fixing bugs, and other stability improvements, there are several new features in this release we're excited to share.

- New internal control plane event management framework to handle changes to the Kubernetes cluster and policies
- Validations to reject/ignore invalid SMI TrafficTarget resources
- Control plane memory utilization improvements; OSM can now be auto-scaled based on memory usage.
- Support for TCP server-first protocols for in-mesh traffic. `appProtocol: tcp-server-first` may now be specified on ports for services within the mesh in addition to services specified in an Egress policy to reduce latency for protocols like MySQL and PostgreSQL.
- The Grafana dashboards shipped with OSM are more accurate and consistent.
- OSM control plane images are now multi-architecture, supporting linux/amd64 and linux/arm64.

The `osm` CLI has also seen several improvements since the last release.

- The `osm support bug-report` command that gathers logs and other information helpful for debugging can now collect logs from OSM's control plane in addition to Pods within the mesh.
- For users managing OSM's lifecycle without Helm, the `osm install` command now supports optionally cleaning up CustomResourceDefinitions, webhook configurations, and resources created by the control plane to streamline uninstallation.
- The `osm version` command will now display the version of OSM installed on your cluster alongside the CLI's version.

We’re truly excited about the course of the OSM project. For those that are new to the project, please visit our [OSM docs website](https://docs.openservicemesh.io) to get started and you can also download the latest version from [the OSM GitHub releases page](https://github.com/openservicemesh/osm/releases). We look forward to hearing from you on our [OSM GitHub repo](https://github.com/openservicemesh/osm/issues).
