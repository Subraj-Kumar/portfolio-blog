---
title: "Optimizing Library Seat Detection with Centroid Tracking"
description: "Why switching from Intersection over Union (IoU) to a point-in-box/centroid method drastically improved accuracy."
pubDate: 2026-06-06
readingTime: "5 min read"
tags: ["Computer Vision", "Python", "OpenCV", "YOLO"]
draft: false
---

### The Problem with IoU

During the development of the Library Seat Occupancy Detection pipeline, I initially relied on standard Intersection over Union (IoU) metrics. However, I quickly discovered that traditional bounding box overlaps created too much noise and false positives when applied to the fixed-angle CCTV feeds inside the library.

### The Point-in-Box Pivot

By engineering a strict point-in-box/centroid tracking method, the system accurately maps a human subject's center of mass directly to fixed seating coordinates, significantly reducing processing overhead and improving real-time reliability for the live dashboard.
