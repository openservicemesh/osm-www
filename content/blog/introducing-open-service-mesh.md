---
title: "Introducing Open Service Mesh"
slug: "introducing-open-service-mesh"
authorname: "Michelle Noorali"
author: "@openservicemesh"
authorlink: "https://twitter.com/openservicemesh"
date: "2020-08-03T05:00:00-07:00"
---

It is no secret that although microservice environments enable portability, allow faster and more frequent deployment cycles, and can even enable organizations to create teams with more specialized areas of concern, they also come with increased needs around solutions for traffic management, security, and observability. The service mesh pattern for these needs is implemented numerous ways across the ecosystem, and Microsoft has been active in the [Service Mesh Interface](https://smi-spec.io) (SMI) community, helping define the specification for a standard set of portable APIs for common service mesh functionality across service mesh implementations. Vendors can implement SMI to ensure that ecosystem tools can work on many meshes while allowing customer choice of mesh provider.

Today we are excited to introduce a new open source project, [Open Service Mesh](https://openservicemesh.io) (OSM), which is a lightweight and extensible service mesh that runs on Kubernetes. OSM enables users to uniformly manage, secure, and observe service-to-service communication in highly dynamic microservice environments. We hope for OSM to be a community-led project that it will spur collaboration on new and existing APIs for SMI. We intend for OSM to have open governance and be in a place where we can easily collaborate with the community, so we have already kicked off the process for donating OSM to the [Cloud Native Computing Foundation](https://cncf.io) (CNCF).
<!--more-->

We intend for OSM to be effortless for Kubernetes operators to install, maintain, and run; at the same time, we are resolved that OSM be simple for the entire community to understand and contribute to. These goals are rooted in customer requests and have led us to three underlying design principles. First, OSM provides a control plane compatible with the SMI specification, to preserve user choice. Next, OSM uses Envoy for the data plane, due to strong community momentum around Envoy. And finally, the overriding philosophy behind OSM features a "no cliffs" design in order to make OSM flexible enough to handle both simple and complex scenarios using both SMI and programming Envoy xDS APIs directly. "I'm thrilled to see OSM join the Envoy family and build a vendor neutral service mesh solution for Kubernetes with an explicit focus on simplicity," says Matt Klein, creator of Envoy.

Scenarios handled for users in OSM include configuring traffic shifting for common deployment scenarios, securing service-to-service communication with automatic mTLS, enforcing fine-grained access control policies for services, observing metrics for debugging and monitoring of services, integrating with native or external certificate management solutions, and onboarding applications onto the mesh with automatic sidecar injection.

We’re excited to refine this mesh, working on OSM with the community as well as learning from it and informing the evolution of the SMI specification in conjunction with the broader SMI community. We’ll be demoing OSM at [KubeCon EU Virtual 2020](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/) as well as in an upcoming [CNCF webinar](https://www.cncf.io/webinars/). We invite you to join us [on GitHub](https://github.com/openservicemesh) to learn and share!      
