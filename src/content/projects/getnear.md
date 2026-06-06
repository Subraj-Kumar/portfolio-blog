---
title: "GetNear - Hyperlocal Marketplace"
description: "A production Android marketplace enabling buyers to broadcast real-time product inquiries to nearby sellers via geolocation."
techStack: ["Flutter", "Firebase", "GCP"]
liveUrl: "https://getnear.net"
---

<div class="grid grid-cols-1 md:grid-cols-2 gap-6 surface-raised p-6 mb-12 rounded-lg mt-8">
  <div>
    <div class="font-label-caps text-on-surface-variant mb-2">GEOSPATIAL QUERYING</div>
    <div class="font-headline-md text-primary">Haversine-Distance Ranking</div>
  </div>
  <div>
    <div class="font-label-caps text-on-surface-variant mb-2">INTELLIGENCE</div>
    <div class="font-headline-md text-primary">Google Cloud Vision API</div>
  </div>
</div>

## System Architecture

GetNear is a production Android marketplace built with Flutter and Dart. The core mechanic relies on a real-time event pipeline where buyers broadcast inquiries, and sellers are dynamically ranked and notified based on proximity.

### Key Implementations

- **Real-time Lifecycle Workflows:** Integrated Firebase Auth (Email/Password, Google Sign-In, Phone OTP, anonymous), Firestore, Cloud Storage, and FCM to handle the entire inquiry lifecycle.
- **Seller States & Deal Tracking:** Engineered a response system handling six distinct availability statuses and verified buyer visit confirmations.
- **AI Integration:** Developed AI-powered product category suggestions utilizing the Google Cloud Vision API upon inquiry photo upload.
- **Role-Based Access Control:** Deployed a Targeted Promotions System and Blood Donation Module, enforcing strict Firestore security rules across Admin, Buyer, Seller, and Donor roles.
