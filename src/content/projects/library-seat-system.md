---
title: "Real-Time Library Seat Occupancy Detection System"
description: "An Edge-to-Cloud Computer Vision & IoT Infrastructure Initiative designed to eliminate student overcrowding and optimize study space utilization."
techStack: ["Python", "OpenCV", "YOLOv8", "FastAPI", "React"]
liveUrl: "https://central-library-jnu-live.vercel.app"
---

<div class="text-center mb-12">
  <div class="inline-block px-4 py-1 rounded-full bg-primary/10 text-primary font-label-caps tracking-widest text-sm mb-4 border border-primary/20">
    SMART CAMPUS INITIATIVE
  </div>
  <p class="text-xl text-on-surface-variant max-w-3xl mx-auto leading-relaxed">
    An end-to-end bridging of physical infrastructure and digital accessibility for the Dr. B.R. Ambedkar Central Library, JNU.
  </p>
</div>

<div class="grid grid-cols-1 md:grid-cols-4 gap-4 surface-raised p-6 mb-16 rounded-xl shadow-lg border border-outline/10">
  <div class="flex flex-col items-center text-center p-4">
    <span class="text-3xl mb-2">📷</span>
    <div class="font-label-caps text-on-surface-variant text-xs tracking-wide">AI CORE</div>
    <div class="font-bold text-primary">YOLOv8 + OpenCV</div>
  </div>
  <div class="flex flex-col items-center text-center p-4">
    <span class="text-3xl mb-2">⚙️</span>
    <div class="font-label-caps text-on-surface-variant text-xs tracking-wide">ORCHESTRATION</div>
    <div class="font-bold text-primary">FastAPI</div>
  </div>
  <div class="flex flex-col items-center text-center p-4">
    <span class="text-3xl mb-2">⚡</span>
    <div class="font-label-caps text-on-surface-variant text-xs tracking-wide">DATA PIPELINE</div>
    <div class="font-bold text-primary">WebSockets</div>
  </div>
  <div class="flex flex-col items-center text-center p-4">
    <span class="text-3xl mb-2">🖥️</span>
    <div class="font-label-caps text-on-surface-variant text-xs tracking-wide">CLIENT LAYER</div>
    <div class="font-bold text-primary">React.js</div>
  </div>
</div>

## 📌 Project Overview

<div class="grid grid-cols-1 md:grid-cols-2 gap-8 my-8">
  <div class="bg-surface-variant/20 p-6 rounded-xl border-l-4 border-error/70">
    <h3 class="text-error font-bold mb-2 flex items-center gap-2"><span class="text-xl">⚠️</span> The Problem</h3>
    <p class="text-on-surface-variant text-sm leading-relaxed">
      In large-scale academic environments, students frequently experience wasted time and disrupted study schedules by physically traveling to central libraries only to find them completely occupied.
    </p>
  </div>
  <div class="bg-surface-variant/20 p-6 rounded-xl border-l-4 border-success/70">
    <h3 class="text-success font-bold mb-2 flex items-center gap-2"><span class="text-xl">💡</span> The Solution</h3>
    <p class="text-on-surface-variant text-sm leading-relaxed">
      By leveraging fixed CCTV hardware, this system processes live spatial data through an advanced machine learning pipeline, dynamically tracks seat utilization, and broadcasts instantaneous occupancy metrics to a modern web dashboard.
    </p>
  </div>
</div>

## 🏗️ System Architecture

The platform is engineered as a decoupled, asynchronous multi-tier system built to handle streaming data with minimal latency.

<div class="bg-[#0d1117] text-[#c9d1d9] p-6 rounded-xl my-6 font-mono text-sm overflow-x-auto shadow-inner border border-outline/20">
<pre><code>[ Local CCTV / Video Stream ] 
             │
             ▼
 🧠  1. Edge AI Processing (YOLOv8 + Custom Anchor Logic)
             │  (HTTP POST / JSON Payload)
             ▼
 🌐  2. Cloud Orchestration Engine (FastAPI Deployment)
             │  (Persistent WebSockets Full-Duplex)
             ▼
 💻  3. Dynamic UI Client Layer (React + Glassmorphic Floor Map)
</code></pre>
</div>

<ul class="space-y-4 mt-6 list-none pl-0">
  <li class="bg-surface-variant/10 p-4 rounded-lg"><strong>Edge AI Processing Layer (Python & OpenCV):</strong> Manages localized frame capture, lightweight inference scaling, and algorithmic spatial validation.</li>
  <li class="bg-surface-variant/10 p-4 rounded-lg"><strong>Cloud Orchestration Engine (FastAPI):</strong> Acts as the centralized ingestion mechanism, state management coordinator, and active client broker.</li>
  <li class="bg-surface-variant/10 p-4 rounded-lg"><strong>Dynamic UI Client Layer (React):</strong> A responsive consumer application delivering real-time reactive feedback to users via persistent network pipelines.</li>
</ul>

---

## 🛠️ Core Engineering & Algorithmic Logic

<div class="relative p-7 mt-10 mb-8 rounded-2xl border border-outline/10 bg-gradient-to-br from-surface-variant/20 to-transparent shadow-sm">
  <div class="absolute -top-4 left-6 bg-surface px-4 py-1 rounded-full border border-outline/10 text-xs font-bold tracking-widest text-primary shadow-sm">
    SYSTEM LOGIC 01
  </div>
  <h3 class="text-xl font-bold flex items-center gap-3 mb-3">
    <span class="text-blue-500">🎯</span> Object Detection Optimization
  </h3>
  <p class="text-on-surface-variant text-sm leading-relaxed">
    The system utilizes a specialized <strong>YOLOv8</strong> (You Only Look Once) convolutional neural network targeted exclusively at class <code>0</code> (Person) tracking. 
  </p>
  <p class="text-on-surface-variant text-sm leading-relaxed border-l-2 border-primary/40 pl-4 ml-1 mt-3">
    <strong>Inference Tuning:</strong> The inference cycle is explicitly rate-limited to an optimal interval ($\Delta t = 0.8\text{s}$) to preserve network overhead and edge-compute resources while ensuring perfectly responsive data synchronization for the end user.
  </p>
</div>

<div class="relative p-7 mb-8 rounded-2xl border border-outline/10 bg-gradient-to-br from-surface-variant/20 to-transparent shadow-sm">
  <div class="absolute -top-4 left-6 bg-surface px-4 py-1 rounded-full border border-outline/10 text-xs font-bold tracking-widest text-primary shadow-sm">
    SYSTEM LOGIC 02
  </div>
  <h3 class="text-xl font-bold flex items-center gap-3 mb-3">
    <span class="text-purple-500">📐</span> Advanced Spatial Alignment
  </h3>
  <p class="text-on-surface-variant text-sm leading-relaxed mb-4">
    Rather than employing standard bounding box intersections (Intersection over Union / IoU), which inherently fail in high-density seating environments due to overlapping visual planes, the system introduces a proprietary <strong>Keypoint Centroid Target Tracking</strong> algorithm:
  </p>
  <ul class="list-none pl-0 space-y-4 text-sm text-on-surface-variant">
    <li class="bg-surface/50 p-4 rounded-lg border border-outline/5">
      <strong>1. Anchor Formulation:</strong> For every person detected, an explicit spatial anchor coordinate $(P_x, P_y)$ is isolated at the bottom-center of the bounding box.
    </li>
    <li class="bg-surface/50 p-4 rounded-lg border border-outline/5">
      <strong>2. Perspective Transform Compensation:</strong> A $10\%$ upward vertical offset is applied to the anchor equation:
      <div class="text-center font-mono text-primary font-bold my-2 bg-surface-variant/30 py-2 rounded">
        $P_y = y_2 - (y_2 - y_1) \times 0.1$
      </div>
      This mathematically shifts the tracking node directly onto the plane of the chair seat, eliminating errors caused by varying human heights or background walking paths.
    </li>
    <li class="bg-surface/50 p-4 rounded-lg border border-outline/5">
      <strong>3. Region Validation:</strong> A swift geometric parsing function confirms entry into the hardcoded static bounding box of a seat $(bx_1, by_1, bx_2, by_2)$:
      <div class="text-center font-mono text-primary font-bold my-2 bg-surface-variant/30 py-2 rounded">
        $bx_1 \le P_x \le bx_2 \quad \land \quad by_1 \le P_y \le by_2$
      </div>
    </li>
  </ul>
</div>

<div class="relative p-7 mb-12 rounded-2xl border border-outline/10 bg-gradient-to-br from-surface-variant/20 to-transparent shadow-sm">
  <div class="absolute -top-4 left-6 bg-surface px-4 py-1 rounded-full border border-outline/10 text-xs font-bold tracking-widest text-primary shadow-sm">
    SYSTEM LOGIC 03
  </div>
  <h3 class="text-xl font-bold flex items-center gap-3 mb-3">
    <span class="text-emerald-500">⏱️</span> Temporal Smoothing Stabilization
  </h3>
  <p class="text-on-surface-variant text-sm leading-relaxed mb-3">
    Computer vision deployments are highly susceptible to tracking "flicker" caused by temporary physical occlusions or sudden changes in lighting. 
  </p>
  <p class="text-on-surface-variant text-sm leading-relaxed border-l-2 border-primary/40 pl-4 ml-1">
    <strong>The Engineering Fix:</strong> To combat this, a state-machine <em>Hysteresis Smoothing Algorithm</em> was engineered. Every seat tracks its state inside an active memory buffer. A status change (e.g., <code>EMPTY</code> $\rightarrow$ <code>OCCUPIED</code>) must remain persistent for a continuous sequence of processing frames (<code>SMOOTHING_FRAMES = 2</code>) before the system updates the global state. This guarantees a rock-solid UI layer that actively filters out noise.
  </p>
</div>

---

## 🔒 Security & Ethical Engineering (Privacy-by-Design)

To align with modern data privacy frameworks and university regulations, compliance was architected directly into the engineering loop:

- 🛡️ **No Biometric Tracking:** The pipeline explicitly blocks facial recognition libraries and strips individual visual characteristics.
- 🗑️ **No Persistent Data Storage:** Video frames are processed strictly in volatile memory (RAM) and immediately discarded. No video streams are saved to local disks or transmitted over public networks.

---

## 📈 Impact & Future Roadmaps

This deployment stands as a successful proof-of-concept demonstrating how consumer-grade AI models can easily modernize legacy institutional infrastructure.

<div class="grid grid-cols-1 md:grid-cols-3 gap-4 mt-6">
  <div class="surface-raised p-5 rounded-lg border-t-4 border-primary shadow-sm">
    <h4 class="font-bold text-primary mb-2 text-sm">Multi-Camera Fusion</h4>
    <p class="text-xs text-on-surface-variant">Merging coordinate mappings across overlapping fields-of-view.</p>
  </div>
  <div class="surface-raised p-5 rounded-lg border-t-4 border-primary shadow-sm">
    <h4 class="font-bold text-primary mb-2 text-sm">Predictive Analytics</h4>
    <p class="text-xs text-on-surface-variant">Integrating Time-Series forecasting models to advise students on peak occupancy hours.</p>
  </div>
  <div class="surface-raised p-5 rounded-lg border-t-4 border-primary shadow-sm">
    <h4 class="font-bold text-primary mb-2 text-sm">Mobile Integration</h4>
    <p class="text-xs text-on-surface-variant">Wrapping the frontend layer into progressive native mobile applications.</p>
  </div>
</div>

<div class="mt-16 mb-8 flex justify-center">
  <a href="https://central-library-jnu-live.vercel.app" target="_blank" rel="noopener noreferrer" class="group relative inline-flex items-center gap-3 px-8 py-4 bg-gradient-to-r from-indigo-600 to-purple-600 text-white rounded-full font-bold tracking-wide hover:-translate-y-1 hover:shadow-lg hover:shadow-purple-500/30 transition-all duration-300 overflow-hidden border border-indigo-400/20">
    <span class="relative flex h-3 w-3">
      <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-white opacity-75"></span>
      <span class="relative inline-flex rounded-full h-3 w-3 bg-white"></span>
    </span>
    <span class="relative z-10 drop-shadow-md">LAUNCH LIVE DASHBOARD</span>
    <svg class="relative z-10 transform group-hover:translate-x-1 transition-transform" xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"></path><path d="m12 5 7 7-7 7"></path></svg>
  </a>
</div>
