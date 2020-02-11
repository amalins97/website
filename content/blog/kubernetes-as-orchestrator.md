---
title: "Kubernetes is NOT a container orchestrator"
date: 2020-02-10T09:39:23+02:00
description: Launching Flanksource
slug: kubernetes-is-not-container-orchestrator
layout: post
author: Moshe Immerman
draft: false
disqus: true
---



It is a common misconception that Kubernetes is a container orchestrator, after-all the website describes it as:

<span class="notification" style="text-align: center; display: block; font-style: italic">open-source system for automating deployment, scaling, and management of <strong>containerized</strong> applications</span>

While this description may be correct, it fails to capture  Kubernetes' true essence.

Kubernetes' ascension can be more readily explained by the amazing and passionate community that has developed, not for its container orchestration prowess, but for some of the following reasons:


### Shared  Language

 Kubernetes decouples *the definition* of an application, from *how* it is deployed. Never before have developers had this common language to describe their applications that is portable to different teams, companies and even clouds.

 20 years from now, we may not be using the Kubernetes codebase, but we will almost certainly be using its declarative model for defining applications.

### Commoditizing Control Theory

At it's core Kubernetes is an enterprise-ready, programmable [hierarchical control system](https://en.wikipedia.org/wiki/Hierarchical_control_system) that consists of dozens of [closed feedback loops](https://en.wikipedia.org/wiki/Control_theory#Open-loop_and_closed-loop_(feedback)_control). These work together to create a system that, while complex at first glance, is transparent, consistent and elegantly simple once you understand the underlying theory.


<table>
<tr>
<td>
<span>
<ul>
<li>Builtin and <a href='https://kubernetes.io/docs/concepts/extend-kubernetes/api-extension/custom-resources/'>custom</a> resources define the desired state declaratively</li>
<li>Controllers reconcile the observed state into desired state</li>
<li>Each control loop can be reasoned about independently</li>
</ul>
</span></td>
<td><img src="/images/control-loop.png"></img></td>
</tr>
</table>

[Operators](https://kubernetes.io/docs/concepts/extend-kubernetes/operator/) and custom resources have commoditized building control loops for anything from [virtual machines](https://kubevirt.io/) to [video encoding and transmission systems](https://youtu.be/7g4da6-JXfE).

To learn more about control theory watch AWS Principal Engineer Colm MacCárthaigh's talk on [PID Loops and the Art of Keeping Systems Stable](https://www.youtube.com/watch?v=3AxSwCC7I4s) or Marc Brookers [blog](https://brooker.co.za/blog/)


### Open

Kubernetes is perhaps one of the few truly open systems. Where else do you get all the major cloud providers, vendors, end-users and independent individuals all collaborating together for a common purpose?

Linux is the next closest *open* system. However, while there is a lot of collaboration upstream, most of the value is delivered in forked kernels that are maintained by each vendor. This makes compatibility between vendors possible, not guaranteed in the way Kubernetes is with *free* conformance tests.

### Governance



Governance is usually a synonym for red-tape that slows things down, while not adding much value. The [Kubernetes Governance Model](https://github.com/kubernetes/community/blob/master/governance.md) is refreshing different. It’s designed to respect Conway’s Law, pushing decision making down to the people with the most knowledge, while at the same time providing democratically elected steering that keeps the massive ship sailing in the right direction.

<div class="centered">
<img src="/images/k8s-governance.png">
</div>


As Kubernetes matures, the governance model has adapted to its current form, in which it heavily encourages de-coupling of new work into sub-projects owned by Special Interest Groups (SIGs).

Members of the Kubernetes [community](https://github.com/kubernetes/community/blob/master/community-membership.md) have a hierarchy with each level providing different rights - predominantly, the differences lie in who can approve code for merging.

Promotion in the hierarchy is based not on seniority or vendor affiliation, but rather on a democratic process of rewarding people for *chopping wood and carrying water* - doing the jobs that need doing, not just the *fun* work.

### Communications

With the scale at which Kubernetes operates, it is amazing to see the level and quality of communication that prevails. Kubernetes certainly didn’t invent any of these techniques, but it certainly has done a fantastic job of implementing them.

##### Everything as a PR

The first thing you notice about the kubernetes communication model is that everything is a pull request or an issue:

* Joining the organization
* Promoting contributors
* Changing policies
* Blog posts
* KEPs (More on this below)

##### #Slack

The  `#kubernetes-users` slack channel has close to 90k members, making it one of the largest if not the largest channel in the world.  Does your company have a slack channel for everyone?

##### Office Hours

There are dozens of scheduled [meetings](https://github.com/kubernetes/community/blob/master/sig-list.md) across all the SIGs and Working Groups (WG) every month. What makes these meetings unique is that they are open to anyone, recorded and published to YouTube with concise minutes that are shared in a public Google doc.


##### Request for Proposals

As projects grow, RFP's become essential to maintaining stability, consistency and speed. Kubernetes Enhancements Proposals ([KEP](https://github.com/kubernetes/enhancements/tree/master/keps)s) have been  great at communicating and coordination change, with them even being adopted by projects like [kafka](https://cwiki.apache.org/confluence/display/KAFKA/Kafka+Improvement+Proposals).




