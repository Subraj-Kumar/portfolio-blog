---
title: "GetNear - Hyperlocal Buyer-Seller Marketplace"
description: "A production Android marketplace enabling buyers to broadcast real-time product inquiries to nearby sellers using dynamic geospatial routing and AI-powered categorizations."
techStack: ["Flutter", "Firebase", "GCP", "Dart"]
liveUrl: "https://getnear.net"
---

<div class="text-center mb-12">
  <div class="inline-block px-4 py-1 rounded-full bg-primary/10 text-primary font-label-caps tracking-widest text-sm mb-4 border border-primary/20">
    PRODUCTION ANDROID APPLICATION
  </div>
  <p class="text-xl text-on-surface-variant max-w-3xl mx-auto leading-relaxed">
    A real-time geospatial event pipeline bridging the gap between local retail inventory and immediate consumer demand.
  </p>
</div>

<div class="grid grid-cols-1 md:grid-cols-4 gap-4 surface-raised p-6 mb-16 rounded-xl shadow-lg border border-outline/10">
  <div class="flex flex-col items-center text-center p-4">
    <span class="text-3xl mb-2">📱</span>
    <div class="font-label-caps text-on-surface-variant text-xs tracking-wide">MOBILE CORE</div>
    <div class="font-bold text-primary">Flutter & Dart</div>
  </div>
  <div class="flex flex-col items-center text-center p-4">
    <span class="text-3xl mb-2">🔥</span>
    <div class="font-label-caps text-on-surface-variant text-xs tracking-wide">BACKEND AS A SERVICE</div>
    <div class="font-bold text-primary">Firebase Suite</div>
  </div>
  <div class="flex flex-col items-center text-center p-4">
    <span class="text-3xl mb-2">🗺️</span>
    <div class="font-label-caps text-on-surface-variant text-xs tracking-wide">GEOSPATIAL & AI</div>
    <div class="font-bold text-primary">Google Cloud (GCP)</div>
  </div>
  <div class="flex flex-col items-center text-center p-4">
    <span class="text-3xl mb-2">🗄️</span>
    <div class="font-label-caps text-on-surface-variant text-xs tracking-wide">REAL-TIME DATA</div>
    <div class="font-bold text-primary">Cloud Firestore</div>
  </div>
</div>

## 📌 Project Overview

<div class="grid grid-cols-1 md:grid-cols-2 gap-8 my-8">
  <div class="bg-surface-variant/20 p-6 rounded-xl border-l-4 border-error/70">
    <h3 class="text-error font-bold mb-2 flex items-center gap-2"><span class="text-xl">⚠️</span> The Problem</h3>
    <p class="text-on-surface-variant text-sm leading-relaxed">
      Consumers waste significant time physically visiting or calling multiple local shops to verify product availability. Conversely, local retailers lack digital visibility for their current, on-shelf inventory to capture nearby intent-driven buyers.
    </p>
  </div>
  <div class="bg-surface-variant/20 p-6 rounded-xl border-l-4 border-success/70">
    <h3 class="text-success font-bold mb-2 flex items-center gap-2"><span class="text-xl">💡</span> The Solution</h3>
    <p class="text-on-surface-variant text-sm leading-relaxed">
      A reverse-commerce model. Buyers broadcast specific product inquiries, and the platform dynamically routes these requests to relevant nearby sellers based on Haversine distance tracking and automated category matching.
    </p>
  </div>
</div>

---

## 🏗️ System Architecture & Key Implementations

<div class="relative p-7 mt-10 mb-8 rounded-2xl border border-outline/10 bg-gradient-to-br from-surface-variant/20 to-transparent shadow-sm">
  <div class="absolute -top-4 left-6 bg-surface px-4 py-1 rounded-full border border-outline/10 text-xs font-bold tracking-widest text-primary shadow-sm">
    CORE MECHANIC 01
  </div>
  <h3 class="text-xl font-bold flex items-center gap-3 mb-3">
    <span class="text-teal-500">📍</span> Geospatial Querying & Routing
  </h3>
  <p class="text-on-surface-variant text-sm leading-relaxed mb-3">
    The application relies on highly optimized location tracking to deliver relevance. Instead of fetching all sellers, the system utilizes <strong>Haversine-Distance Algorithms</strong> integrated directly into the querying layer. 
  </p>
  <p class="text-on-surface-variant text-sm leading-relaxed border-l-2 border-primary/40 pl-4 ml-1">
    <strong>Execution:</strong> When a buyer drops a pin or uses their live GPS, the Firebase Cloud Functions calculate the radial distance, instantly filtering and push-notifying (via FCM) only the sellers who are within the targeted operational radius.
  </p>
</div>

<div class="relative p-7 mb-8 rounded-2xl border border-outline/10 bg-gradient-to-br from-surface-variant/20 to-transparent shadow-sm">
  <div class="absolute -top-4 left-6 bg-surface px-4 py-1 rounded-full border border-outline/10 text-xs font-bold tracking-widest text-primary shadow-sm">
    CORE MECHANIC 02
  </div>
  <h3 class="text-xl font-bold flex items-center gap-3 mb-3">
    <span class="text-amber-500">⚡</span> Real-Time Lifecycle Workflows
  </h3>
  <p class="text-on-surface-variant text-sm leading-relaxed mb-3">
    Managing the transition from an "Open Inquiry" to a "Closed Deal" required a robust state machine.
  </p>
  <ul class="list-none pl-0 space-y-3 text-sm text-on-surface-variant ml-1 border-l-2 border-primary/40 pl-4">
    <li><strong>Seller States:</strong> Engineered a response system capable of handling 6 distinct availability and negotiation statuses (e.g., In-Stock, Out-of-Stock, Alternative Available).</li>
    <li><strong>1:1 Chat Infrastructure:</strong> Built a real-time, low-latency messaging layer using Firestore listeners to facilitate direct buyer-seller negotiations and Admin support ticketing.</li>
    <li><strong>Visit Intent:</strong> Integrated logic to securely track when a buyer confirms physical visit intentions, directly tying digital discovery to foot traffic conversions.</li>
  </ul>
</div>

<div class="relative p-7 mb-8 rounded-2xl border border-outline/10 bg-gradient-to-br from-surface-variant/20 to-transparent shadow-sm">
  <div class="absolute -top-4 left-6 bg-surface px-4 py-1 rounded-full border border-outline/10 text-xs font-bold tracking-widest text-primary shadow-sm">
    CORE MECHANIC 03
  </div>
  <h3 class="text-xl font-bold flex items-center gap-3 mb-3">
    <span class="text-blue-500">🧠</span> Vision AI & Smart Categorization
  </h3>
  <p class="text-on-surface-variant text-sm leading-relaxed mb-3">
    To reduce friction during the inquiry creation process, I developed an AI-powered image analysis pipeline.
  </p>
  <p class="text-on-surface-variant text-sm leading-relaxed border-l-2 border-primary/40 pl-4 ml-1">
    <strong>Execution:</strong> When a user uploads a reference photo for a product they want, the system triggers the <strong>Google Cloud Vision API</strong>. It dynamically parses the image, extracts keyword entities, and automatically suggests relevant product categories and multi-tags, vastly improving seller matching accuracy.
  </p>
</div>

---

## 🔒 Security & Access Control

With multiple user types interacting within the same environment, strict data siloing was paramount.

- 🛡️ **Role-Based Security Rules:** Deployed complex Firestore Security Rules to isolate data streams between <strong>Admins, Buyers, Sellers, and Donors</strong>. Sellers cannot read other sellers' private negotiations, and buyers only access public merchant profiles.
- 🔐 **Multi-Factor Authentication:** Integrated Google Sign-In, Email/Password, and strict Phone OTP flows to prevent duplicate spam accounts and verify merchant legitimacy.
- 🩸 **Independent Module Architectures:** Successfully integrated parallel systems, such as a localized Blood Donation Module and a Targeted Promotions system, without polluting the core e-commerce data structures.

---

<div class="mt-16 mb-8 flex justify-center">
  <a href="https://getnear.net" target="_blank" rel="noopener noreferrer" class="group relative inline-flex items-center gap-3 px-8 py-4 bg-gradient-to-r from-emerald-600 to-teal-600 text-white rounded-full font-bold tracking-wide hover:-translate-y-1 hover:shadow-lg hover:shadow-teal-500/30 transition-all duration-300 overflow-hidden border border-teal-400/20">
    <span class="relative flex h-3 w-3">
      <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-white opacity-75"></span>
      <span class="relative inline-flex rounded-full h-3 w-3 bg-white"></span>
    </span>
    <span class="relative z-10 drop-shadow-md">VISIT GETNEAR.NET</span>
    <svg class="relative z-10 transform group-hover:translate-x-1 transition-transform" xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"></path><path d="m12 5 7 7-7 7"></path></svg>
  </a>
</div>
