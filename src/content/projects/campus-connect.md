---
title: "CampusConnect - Role-Based Event Management Platform"
description: "A cloud-native, full-stack web application designed to digitize and centralize university events with strict RBAC, JWT OAuth, and automated asset lifecycles."
techStack: ["React", "Node.js", "MongoDB", "OAuth 2.0"]
liveUrl: "https://campus-connect-se.vercel.app"
---

<div class="text-center mb-12">
  <div class="inline-block px-4 py-1 rounded-full bg-primary/10 text-primary font-label-caps tracking-widest text-sm mb-4 border border-primary/20">
    CLOUD-NATIVE ARCHITECTURE
  </div>
  <p class="text-xl text-on-surface-variant max-w-3xl mx-auto leading-relaxed">
    A secure digital ecosystem built to digitize and centralize university events, completely eliminating scattered campus communication networks.
  </p>
</div>

<div class="grid grid-cols-1 md:grid-cols-4 gap-4 surface-raised p-6 mb-16 rounded-xl shadow-lg border border-outline/10">
  <div class="flex flex-col items-center text-center p-4">
    <span class="text-3xl mb-2">🔐</span>
    <div class="font-label-caps text-on-surface-variant text-xs tracking-wide">AUTH & SECURITY</div>
    <div class="font-bold text-primary">OAuth 2.0 + JWT</div>
  </div>
  <div class="flex flex-col items-center text-center p-4">
    <span class="text-3xl mb-2">⚙️</span>
    <div class="font-label-caps text-on-surface-variant text-xs tracking-wide">BACKEND API</div>
    <div class="font-bold text-primary">Node + Express</div>
  </div>
  <div class="flex flex-col items-center text-center p-4">
    <span class="text-3xl mb-2">🗄️</span>
    <div class="font-label-caps text-on-surface-variant text-xs tracking-wide">DATABASE</div>
    <div class="font-bold text-primary">MongoDB Atlas</div>
  </div>
  <div class="flex flex-col items-center text-center p-4">
    <span class="text-3xl mb-2">☁️</span>
    <div class="font-label-caps text-on-surface-variant text-xs tracking-wide">CDN & STORAGE</div>
    <div class="font-bold text-primary">Cloudinary</div>
  </div>
</div>

## 📌 Project Overview

<div class="grid grid-cols-1 md:grid-cols-2 gap-8 my-8">
  <div class="bg-surface-variant/20 p-6 rounded-xl border-l-4 border-error/70">
    <h3 class="text-error font-bold mb-2 flex items-center gap-2"><span class="text-xl">⚠️</span> The Problem</h3>
    <p class="text-on-surface-variant text-sm leading-relaxed">
      Campus communication is often highly fragmented. Relying on scattered WhatsApp groups and physical notice boards leads to poor event visibility, registration bottlenecks, and disjointed management.
    </p>
  </div>
  <div class="bg-surface-variant/20 p-6 rounded-xl border-l-4 border-success/70">
    <h3 class="text-success font-bold mb-2 flex items-center gap-2"><span class="text-xl">💡</span> The Solution</h3>
    <p class="text-on-surface-variant text-sm leading-relaxed">
      A strict Role-Based Access Control (RBAC) web application dynamically rendering customized dashboards for Students, Event Organizers, and Admins across distributed, highly-scalable cloud platforms.
    </p>
  </div>
</div>

---

## ✨ Key Features

<ul class="space-y-4 mt-8 list-none pl-0">
  <li class="bg-surface-variant/10 p-6 rounded-xl border border-outline/5 hover:border-primary/30 transition-colors shadow-sm">
    <h4 class="font-bold text-primary mb-2 flex items-center gap-2 text-lg"><span>🛡️</span> Frictionless Onboarding & Auth</h4>
    <p class="text-sm text-on-surface-variant">Integrated Google OAuth 2.0 via Passport.js to provide secure, one-tap login. This eliminates password fatigue while utilizing secure, encrypted JSON Web Tokens (JWT) for stateless cross-domain session management.</p>
  </li>
  
  <li class="bg-surface-variant/10 p-6 rounded-xl border border-outline/5 hover:border-primary/30 transition-colors shadow-sm">
    <h4 class="font-bold text-primary mb-2 flex items-center gap-2 text-lg"><span>🎭</span> Role-Based Access Control (RBAC)</h4>
    <p class="text-sm text-on-surface-variant mb-3">Architected strict routing and data scoping protocols directly tied to user authentication roles:</p>
    <ul class="list-disc pl-6 text-sm text-on-surface-variant space-y-2">
      <li><strong>Students:</strong> Can browse upcoming events, seamlessly register with their academic profiles, and receive instant confirmation states.</li>
      <li><strong>Organizers:</strong> Can create events, securely upload promotional posters to a Cloudinary CDN, and track real-time registration analytics.</li>
      <li><strong>Admins:</strong> Possess global oversight with a moderation workflow to approve or reject organizer accounts, preventing spam and unauthorized platform access.</li>
    </ul>
  </li>

  <li class="bg-surface-variant/10 p-6 rounded-xl border border-outline/5 hover:border-primary/30 transition-colors shadow-sm">
    <h4 class="font-bold text-primary mb-2 flex items-center gap-2 text-lg"><span>⏱️</span> Automated Data Lifecycle</h4>
    <p class="text-sm text-on-surface-variant">Engineered a background <code>node-cron</code> job that runs daily on the Express server to automatically purge events and orphaned image assets older than 30 days, heavily optimizing cloud database storage and bandwidth costs.</p>
  </li>
</ul>

---

## 🧠 Technical Challenges Overcome

<div class="relative p-7 mt-10 mb-8 rounded-2xl border border-outline/10 bg-gradient-to-br from-surface-variant/20 to-transparent shadow-sm">
  <div class="absolute -top-4 left-6 bg-surface px-4 py-1 rounded-full border border-outline/10 text-xs font-bold tracking-widest text-primary shadow-sm">
    CHALLENGE 01
  </div>
  <h3 class="text-xl font-bold flex items-center gap-3 mb-3">
    <span class="text-blue-500">🌐</span> Decoupled Architecture & CORS
  </h3>
  <p class="text-on-surface-variant text-sm leading-relaxed mb-3">
    Transitioning the application from a local development environment to the public internet required mitigating strict Cross-Origin Resource Sharing (CORS) policies. 
  </p>
  <p class="text-on-surface-variant text-sm leading-relaxed border-l-2 border-primary/40 pl-4 ml-1">
    <strong>The Engineering Fix:</strong> Because the React frontend and Express backend were hosted on entirely separate domains (Vercel and Render), I configured highly secure pre-flight request handling and proxy routing to ensure seamless, credentialed API communication across the cloud ecosystem.
  </p>
</div>

<div class="relative p-7 mb-8 rounded-2xl border border-outline/10 bg-gradient-to-br from-surface-variant/20 to-transparent shadow-sm">
  <div class="absolute -top-4 left-6 bg-surface px-4 py-1 rounded-full border border-outline/10 text-xs font-bold tracking-widest text-primary shadow-sm">
    CHALLENGE 02
  </div>
  <h3 class="text-xl font-bold flex items-center gap-3 mb-3">
    <span class="text-rose-500">🛡️</span> Bypassing Cloud Provider SMTP Firewalls
  </h3>
  <p class="text-on-surface-variant text-sm leading-relaxed mb-3">
    During the implementation of the NodeMailer event registration confirmation service, the cloud hosting provider actively blocked outbound traffic on standard SMTP ports (465, 587) to combat spam.
  </p>
  <p class="text-on-surface-variant text-sm leading-relaxed border-l-2 border-primary/40 pl-4 ml-1">
    <strong>The Engineering Fix:</strong> To ensure uninterrupted user flow without relying on paid enterprise infrastructure, I engineered a <em>"Mock Service" pattern</em>. This safely resolves the email promises and logs transactional payloads to the server console, demonstrating modular logic that can be instantly swapped for a third-party API (like SendGrid) in a paid production environment.
  </p>
</div>

<div class="relative p-7 mb-12 rounded-2xl border border-outline/10 bg-gradient-to-br from-surface-variant/20 to-transparent shadow-sm">
  <div class="absolute -top-4 left-6 bg-surface px-4 py-1 rounded-full border border-outline/10 text-xs font-bold tracking-widest text-primary shadow-sm">
    CHALLENGE 03
  </div>
  <h3 class="text-xl font-bold flex items-center gap-3 mb-3">
    <span class="text-emerald-500">🔄</span> OAuth Redirect Protocol Synchronization
  </h3>
  <p class="text-on-surface-variant text-sm leading-relaxed mb-3">
    Integrating Google OAuth required precise handling of redirect URIs across dynamic, containerized cloud environments.
  </p>
  <p class="text-on-surface-variant text-sm leading-relaxed border-l-2 border-primary/40 pl-4 ml-1">
    <strong>The Engineering Fix:</strong> I successfully mapped the Google Cloud Console credentials to route through the Render API's reverse proxy, maintaining strict HTTPS integrity, before securely bouncing the authenticated user back to the Vercel frontend with an encrypted URL token payload.
  </p>
</div>

<div class="mt-16 mb-8 flex justify-center">
  <a href="https://campus-connect-se.vercel.app" target="_blank" rel="noopener noreferrer" class="group relative inline-flex items-center gap-3 px-8 py-4 bg-gradient-to-r from-blue-600 to-indigo-600 text-white rounded-full font-bold tracking-wide hover:-translate-y-1 hover:shadow-lg hover:shadow-blue-500/30 transition-all duration-300 overflow-hidden border border-blue-400/20">
    <span class="relative flex h-3 w-3">
      <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-white opacity-75"></span>
      <span class="relative inline-flex rounded-full h-3 w-3 bg-white"></span>
    </span>
    <span class="relative z-10 drop-shadow-md">LAUNCH LIVE PLATFORM</span>
    <svg class="relative z-10 transform group-hover:translate-x-1 transition-transform" xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"></path><path d="m12 5 7 7-7 7"></path></svg>
  </a>
</div>
