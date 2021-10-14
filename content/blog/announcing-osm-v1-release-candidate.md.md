---
title: "Announcing OSM v1.0.0 Release Candidate"
slug: "announcing-osm-v1-release-candidate"
authorname: "OSM maintainers"
author: "@openservicemesh"
authorlink: "https://twitter.com/openservicemesh"
date: "2021-10-14T08:00:00-07:00"
---

Today, we are excited to announce the [first release candidate](https://github.com/openservicemesh/osm/releases/tag/v1.0.0-rc.1) of Open Service Mesh (OSM) v1.0. It has been an exciting year since the initial open sourcing of the OSM project. OSM is a cloud native service mesh that allows you to uniformly manage, secure and observe application traffic in dynamic microservice environments. It runs on Kubernetes today and we’re planning to support OSM in multi-cluster and hybrid environments as well soon. With the v1.0 release coming in the next few weeks, we’ll deliver a stable set of robust service mesh features. You can use OSM to...

<!--more-->

* Take advantage of automatic service to service traffic encryption (mTLS).
* Enforce access control between applications communicating within the mesh, for HTTP, TCP, and gRPC traffic.  
* Split traffic for canary and blue/green style deployments.
* Understand how application traffic is behaving with the traffic metrics OSM collects and exposes.
* Define fine grained traffic control for ingress and egress traffic.
* And more

Check out our newly updated [documentation website](https://docs.openservicemesh.io/) for more information on features, demos, and architecture.

We’ve also spent time over the last year integrating with and contributing to projects in the cloud native ecosystem where we want to guarantee interoperability. [Contour](https://projectcontour.io/), a high performance ingress controller for Kubernetes, is one such project. You can learn how to leverage [Contour for ingress with OSM](https://docs.openservicemesh.io/docs/demos/ingress_contour/). You can also integrate [OSM with Flagger](https://docs.flagger.app/tutorials/osm-progressive-delivery) to unlock progressive delivery functionality and integrate [Open Policy Agent with OSM](https://docs.openservicemesh.io/docs/guides/integrations/external_auth_opa/#osm-with-opa-plugin-external-authorization-walkthrough) using the OPA Envoy plugin. We also continue to learn from and contribute back to the Service Mesh Interface (SMI) project and welcome more implementations and integrations with ecosystem tools in the SMI community.

Thank you to everyone who has helped get OSM to this exciting milestone, given feedback and encouragement, and contributed to this project. We’re very excited for the next chapter of OSM. We hope to learn from and improve upon in-production experiences, add more exciting features, and improve user experience and debuggability. Feedback and contributions are always welcome, and you can join us for a [CNCF webinar on October 26th, 2021](https://community.cncf.io/events/details/cncf-cncf-online-programs-presents-cncf-live-webinarsecuring-your-workload-communications-with-open-service-mesh/) Feel free to open an [issue](https://github.com/openservicemesh/osm/issues), contact us via the Open Service Mesh [mailing list](https://groups.google.com/g/openservicemesh), [slack channel](https://cloud-native.slack.com/archives/C018794NV1C) or join meetings to become involved in the [OSM community](https://github.com/openservicemesh/osm/#community).