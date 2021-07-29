---
title: "Multicluster Service Mesh"
slug: "multicluster-service-mesh"
authorname: "Annie Wang"
author: "@annieee_wang"
authorlink: "https://twitter.com/annieee_wang"
date: "2021-07-29T08:00:00-07:00"
---


While [Open Service Mesh](https://openservicemesh.io/) (OSM) provides microservices environments with tools for security, traffic management, and observability, the project continues to evolve to support changing needs. As users deploy increasingly complex applications to Kubernetes, it’s become evident that running a service mesh across multiple clusters is desirable for application scalability and robustness. 

<!--more-->

As a result, we are excited to discuss our approach and philosophy to expanding OSM and resolving any such limitations with a Multicluster functionality. Our goal for the Multicluster functionality on OSM is to allow users to scale and deploy complex applications, while maintaining that, like OSM, it is effortless to install, maintain, and run. 

With Multicluster, we intend to enable users to horizontally scale their applications under a service mesh by deploying the mesh to more than one cluster. This allows users to exceed the scalability limitations of a single Kubernetes cluster. 

Beyond scale, in the case of cluster degradation or outage, user workloads may suffer an outage when only deployed to a single Kubernetes cluster. Multicluster enables failover and disaster recovery in these situations by deploying services to more than one cluster, as well as targeting traffic away from unhealthy clusters. 

In addition, Multicluster provides affinitized routing through east-west traffic, so pods in one cluster don’t need to exit the cluster to access the ingress of another cluster to communicate with the pods in the second cluster, a behavior known as north-south traffic. 

Lastly, Multicluster enables zero downtime between Kubernetes upgrades, ensuring that customer workloads remain running during upgrades. With multiple clusters, users can stage the upgrades of Kubernetes versions to prevent disruption of services from other clusters while promoting high availability.

While we move towards these feature goals, we plan to keep the installation, maintenance, and running process of Multicluster as simple as possible. We intend to erase the cluster boundaries to create one logical, large cluster with cross cluster service discovery and a single-entry point to simplify configuration. 

As we also continue to contribute to the [Service Mesh Interface](https://smi-spec.io/) (SMI) community, we intend to prove out the Multicluster concept and determine the value to users to help shape how this functionality might fit within the specification. 

We’re excited to continue building out [Multicluster functionality for OSM](https://github.com/openservicemesh/osm/issues/3456) and learning from it. We invite you to join us in building out this exciting functionality. We’d love to hear your experiences and thoughts on our approach – please come to our [monthly community call](https://github.com/openservicemesh/osm#community) and join us on [Github](https://github.com/openservicemesh/osm#readme) to learn more and contribute! 
