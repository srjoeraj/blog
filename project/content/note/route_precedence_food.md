---
title : "Route Precedence is like satisfying your food cravings! 🍲🌮🍝"
subtitle : ""
showInHome : True
date : 2023-11-17
---

Imagine you're a hungry kid (End-user) in a network, and your parents (routers) need to decide what food (route) to order for you. Here's how Route Precedence works:

**Longest prefix 📏**:
The route with the longest IP prefix (subnet mask) for the incoming traffic gets priority. It's like ordering your favourite Karhai Chicken because it matches your preferences.

**Administrative Distance 🚦**:
Routers look at Administrative Distance to determine trustworthiness when routes have the same prefix. Static routes are the most trusted (your parents know your favourite), followed by BGP, EIGRP, OSPF, IS-IS, and RIP. The most trusted route enters the routing table.

**Metric 📊**:
The last factor is the protocol's metric. Suppose identical routes are from the same protocol. Each protocol has its way of calculating metrics, but lower is better. The route with the lowest metric is added to the routing table, just like choosing the tastiest dish when all else is equal.

**Load Balancing 🔄**:
When all factors are equal, and you have two routes that are identical in every way, both routes get to join the routing table, and traffic is load-balanced between them. It's like having two equally tempting desserts on your plate - why settle for one when you can enjoy both?

[Explore more in Jeremy McDowell's dynamic routing videos 📹](https://lnkd.in/ghe7cFMV).<br>
[Dive into Neil Anderson's explanation of Administrative Distance 📹](https://lnkd.in/g5_xsaCf).

Happy routing and bon appétit! 🌐🍽️

<p>#carrers #networking #learning #routing #routingprotocols #networkadministration #studying #tech #growth  #experience #cisco #preperation #engineering #ccna #techhumor #humor</p>
