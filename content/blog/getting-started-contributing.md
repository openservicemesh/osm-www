---
title: "Getting started with contributing to OSM"
slug: "getting-started-contributing"
authorname: "Sanya Kochhar"
author: "@sanya_kochhar"
authorlink: "https://twitter.com/sanya_kochhar"
date: "2021-06-29T08:00:00-07:00"
---



Getting started with contributing to any open source project can seem daunting. [KubeCon + CloudNativeCon](https://www.cncf.io/kubecon-cloudnativecon-events/) gets us energized and ready to contribute to projects, but how do we maintain that momentum and onboard onto a new codebase? Here are five steps that helped new maintainers of Open Service Mesh create that first pull request, followed by links to OSM-relevant resources. This friendly guide comes from first-hand onboarding experience, sprinkled with insight from open source veterans on our team. Let’s get started!

<!--more-->

### :muscle: Get hands-on
First things first: fork and clone the repo. This may seem like an obvious step, but sometimes we tend to dig around on GitHub hoping that documentation will show us exactly how to get started. Getting over that contributing inertia happens when you start digging around in the code and understanding the structure of the codebase. Build the source code. Push your image somewhere. Break something and put it back together again. To get your GitHub workflow set up, follow [our pull request workflow](https://github.com/openservicemesh/osm/blob/main/CONTRIBUTING.md#pull-request-workflow) steps.

### :dancer: Demo time
Take the demos for a spin! Start with the [automated demo](https://docs.openservicemesh.io/docs/getting_started/auto_demo/) to see how OSM interacts with applications, applies policies, and the like. Then move on to the [manual demo](https://docs.openservicemesh.io/docs/getting_started/manual_demo/) which will walk you through applying SMI policies yourself and help you dig into how OSM works so as to understand the different traffic policy modes.

### :female_detective: Code as source of truth
Let the code teach you everything you need to know about the project. Pick a code path to follow — for me, the entry point was the `cmd/cli` directory where I added the `osm mesh list` command. Looking around this directory helped me learn what a user can do with the OSM CLI as well as how various commands are written. As a brand new Go developer and Kubernetes user, I found this was a great way to figure out what I needed in my toolkit. I learned how to navigate unit testing in Go, and I became familiar with the Kubernetes API and documentation. In my experience, another great starting point in many projects is the test suite. Tests illustrate how maintainers expect the code to behave, so looking through each test will guide you through what its parent code does. In OSM, we are constantly looking to grow our test suite and have left some issues open for tests to be written: low-hanging fruit for new contributors!

### :wrench:  Start small
Find a typo or a sentence that makes no sense to you in our [OSM docs](https://docs.openservicemesh.io/), and go fix it in the [OSM docs repo on GitHub](https://github.com/openservicemesh/osm-docs). Getting your first contribution merged helps to get over that initial obstacle of feeling like a newcomer to the project. If it feels intimidating, here is your reminder that we appreciate all improvements, from typo fixes to entire refactors - no PR is too small, and it will feel great when your pull request is merged and you show up as a contributor! If you find a bug you don't know how to address, [open an issue](https://github.com/openservicemesh/osm/issues/new/choose) and we will take a look.

### <img src="/images/octocat.png" height="24" width="24"> Good first issues
Look around in the [good first issue list](https://github.com/openservicemesh/osm/contribute); these are tasks specifically tagged by maintainers to help new contributors find a good entry point into the project. Find one that isn’t assigned to someone already, leave a comment that you’re working on it, try to address it and open a PR to get reviews. Maintainers are happy to help you and ready to give you feedback. If starting with a PR seems daunting, reach out to us on the CNCF Slack (#openservicemesh) to get help in a more private forum.


:link: Now that you have some ideas on ways to get started, here are some links to inform and inspire:

* [CONTRIBUTING.md](https://github.com/openservicemesh/osm/blob/main/CONTRIBUTING.md) - a one-stop shop to understand what goes into a PR. This guide will tell you how to get your repository forked and cloned to keep your fork up to date properly. It also specifies the criteria to get a pull request approved and outlines a commit style guideline for writing some nicely descriptive commit messages.
* [Development guide](https://github.com/openservicemesh/osm/tree/main/docs/dev_guide) – this will help you get your environment set up and ready for development. This guide walks you through building the OSM image and testing your changes and covers the basics of the OSM Helm chart.
* [DESIGN.md](https://github.com/openservicemesh/osm/blob/main/DESIGN.md) - this is a more in-depth review of OSM’s design. This guide talks you through some use cases, explains the various OSM components, and gets you up to speed on all the jargon. This is a big one and should be consumed in moderation, not all at once.
* OSM [Automated Demo](https://docs.openservicemesh.io/docs/getting_started/auto_demo/) and [Manual Demo](https://docs.openservicemesh.io/docs/getting_started/manual_demo/)
* [Navigating the service mesh ecosystem](https://www.cncf.io/online-programs/navigating-the-service-mesh-ecosystem/) – a talk by Lachlan Evenson that explains some key service mesh concepts through the lenses of SMI & OSM.
* [OSM Contributor Ladder](https://github.com/openservicemesh/osm/blob/main/CONTRIBUTOR_LADDER.md) – an outline of the different contributor roles in the project and how to move up the ladder in responsibilities.

We’re happy you’re here and excited to learn about your ideas. See you [in the community and on GitHub](https://github.com/openservicemesh/osm#community)!
