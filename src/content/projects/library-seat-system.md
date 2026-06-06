---
title: "Library Seat Availability System"
description: "An end-to-end computer vision pipeline with live CCTV feeds and YOLO-based object detection for real-time seat occupancy tracking."
techStack: ["Python", "OpenCV", "YOLO"]
liveUrl: "https://central-library-jnu-live.vercel.app"
---

<div class="grid grid-cols-1 md:grid-cols-2 gap-6 surface-raised p-6 mb-12 rounded-lg mt-8">
  <div>
    <div class="font-label-caps text-on-surface-variant mb-2">VISION ENGINE</div>
    <div class="font-headline-md text-primary">YOLO Object Detection</div>
  </div>
  <div>
    <div class="font-label-caps text-on-surface-variant mb-2">DASHBOARD UI</div>
    <div class="font-headline-md text-primary">React + Flask REST API</div>
  </div>
</div>

## Computer Vision Pipeline

Built an end-to-end pipeline connecting live CCTV feeds to a Python and OpenCV backend. The system was engineered to significantly reduce student library search time by providing a live dashboard of available seats.

### Centroid Tracking Methodology

To ensure maximum accuracy with fixed-angle CCTV feeds inside the library environment, I explicitly bypassed traditional Intersection over Union (IoU) overlaps. Instead, the detection logic heavily relies on a strict point-in-box/centroid methodology. This maps a human subject's center of mass directly to fixed seating coordinates, eliminating false positives caused by overlapping bounding boxes in crowded frames.
