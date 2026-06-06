---
title: "C++ Mini Browser Engine"
description: "A lightweight, from-scratch implementation of a web browser engine. Designed to explore the intricacies of HTML parsing, CSS box model computation, and low-level rendering pipelines using modern C++ and OpenGL."
techStack: ["C++", "OpenGL", "V8"]
---

<div class="grid grid-cols-1 md:grid-cols-3 gap-6 surface-raised rounded-lg p-6 mb-section-gap mt-8">
  <div>
    <div class="font-label-caps text-label-caps text-on-surface-variant mb-2">MEMORY FOOTPRINT</div>
    <div class="font-headline-md text-headline-md text-primary">< 50MB</div>
  </div>
  <div>
    <div class="font-label-caps text-label-caps text-on-surface-variant mb-2">RENDER TARGET</div>
    <div class="font-headline-md text-headline-md text-primary">60 FPS</div>
  </div>
  <div>
    <div class="font-label-caps text-label-caps text-on-surface-variant mb-2">CORE METRIC</div>
    <div class="font-headline-md text-headline-md text-primary">Zero-Copy</div>
  </div>
</div>

## Architecture & Pipeline

This project focuses heavily on the core mechanics of parsing and rendering local HTML documents. To maintain strict scope and technical feasibility, complex JavaScript execution environments were intentionally bypassed...
