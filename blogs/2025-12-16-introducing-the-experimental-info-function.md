---
title: "Introducing the Experimental info() Function"
url: "https://prometheus.io/blog/2025/12/16/introducing-info-function/"
date: "2025-12-16"
author: "Arve Knudsen"
feed_url: "https://prometheus.io/blog/feed.xml"
---
Enriching metrics with metadata labels can be surprisingly tricky in Prometheus, even if you're a PromQL wiz! The PromQL join query traditionally used for this is inherently quite complex because it has to specify the labels to join on, the info metric to join with, and the labels to enrich with. The new, still experimental info() function, promises a simpler way, making label enrichment as simple as wrapping your query in a single function call.
