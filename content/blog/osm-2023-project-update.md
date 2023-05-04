---
title: "OSM Project Update"
slug: "osm-project-update"
authorname: "OSM maintainers"
author: "@openservicemesh"
authorlink: "https://twitter.com/openservicemesh"
date: "2023-05-04T08:00:00-07:00"
---

[Open Service Mesh (OSM) was introduced in August 2020](https://openservicemesh.io/blog/introducing-open-service-mesh/) and joined the CNCF shortly after. Since then, OSM has been working closely with the community to provide a simplified operational service mesh experience that makes use of an interoperable set of service mesh APIs via [Service Mesh Interface (SMI)](https://smi-spec.io/).

An incredible amount of excitement, advancements, and shared ideas have emerged in the service mesh community, aligning with OSM’s guiding principles. OSM’s charter has always been to provide a service mesh experience that is focused on being easy to consume and operate. Likewise, [Istio](https://istio.io/), another service mesh community project, simplifies operations as well, and the Istio project continues to evolve and support a new set of use cases and features for the advancement of future workloads, such as a sidecar-less pattern. With the [announcement of the Istio project joining the CNCF](https://istio.io/latest/blog/2022/istio-accepted-into-cncf/), the OSM team is excited to work more closely with the Istio community. This collaboration will result in the OSM project proceeding towards project archival with the CNCF as we focus our team resources on the Istio project.

## Service Mesh Maturity

As cloud native adoption continues to gain momentum, users require the core features and extensibility service meshes provide to support their cloud native microservices more than ever. Enhancements such as the [Kubernetes Gateway API](https://gateway-api.sigs.k8s.io/) and the [Gateway API for Mesh Management and Administration (GAMMA)](https://gateway-api.sigs.k8s.io/contributing/gamma/) further underscore the critical importance and maturity of a service mesh in today’s cloud native stack.

As such, service meshes are evolving to meet the needs of future cloud native workloads, and that is the focus for the OSM team in terms of project roadmap and technical decisions. We see the continued commitment in the community to provide a simplified operational experience for service mesh users as a critical place of investment both in time and resources. With the community making investments in areas such as features like the Gateway API through GAMMA for a standard set of service mesh APIs and sidecar-less proxy patterns, we see these as areas that inspire a collective effort. These community-led initiatives provide a solid foundation to increase collaboration and create a more sustainable service mesh ecosystem.

## The Path Forward

The OSM maintainers are excited to collaborate with the Istio community, along with project collaboration with Gateway API and GAMMA, under the strong governance and collaborative ecosystem provided by the CNCF. The Istio project continues to evolve to support a newer set of use cases and features such as a sidecar-less pattern with the [Ambient mesh announcement](https://istio.io/latest/blog/2022/introducing-ambient-mesh/).

The OSM team has always been committed to meeting the needs of the community to deliver much-needed service mesh features to solve the current issues and develop the next generation of service mesh technologies. This decision will allow the team to help accelerate that realization. Additionally, there will be no more new releases of OSM.

Currently there are immediate areas of interest and collaboration with Istio such as enhancing Istio’s mesh certificate management experience using Kubernetes’ ClusterTrustBundles feature ([RFC: ClusterTrustBundle Integration with Istio](https://docs.google.com/document/d/1eVKo57JVQ8QGjqRkMYGHDraS_vANJf3tTUWqqbvcylQ/edit)), proposing a “safe mode” feature approach for Istio to provide a simplified way to guard the feature use to the most stable APIs for mission critical enterprise environments ([Proposal: Istio Safe Mode](https://docs.google.com/document/d/1aaORW2Ak4Vfpr-N68Q04qS7iskDdF3v7lcZFQsFA_L0/edit)), working on enhancing the telemetry experience of Istio, and collaborating with Istio’s newly announced sidecar-less Ambient Mesh pattern. Given the number of shared goals, the OSM team sees this as an effective and efficient way to collaborate and move the community forward. We are excited to announce this effort and look forward to the onboarding of more contributors and maintainers in shaping the development of the next generation of service meshes. If you have not done so already, please consider joining the CNCF slack channels for Istio to be part of the current and future discussions on Istio.
