# STEMMate-Namibia-A4
STEMMate Namibia — Task 12: Sync Recovery & Production Readiness

Author: Naobeb

Project: STEMMate Vertical Slice Implementation

Module / Assessment: A4 Architecture & Implementation

Overview

This repository contains the standalone vertical slice implementation for Task 10 (Authentication & Offline Session), Task 11 (Task & Content Management), and Task 12 (Sync Recovery & Deployment Setup) for the STEMMate Namibia project.

The focus of Task 12 is ensuring seamless offline-first capability, automated sync recovery after network disruptions, data integrity across IndexedDB and local stores, and a lightweight, dependency-free setup ready for deployment.

Key Features (Task 12 Focus)

Automatic Network State Detection

Real-time listeners for online and offline browser events.

Visual badge indicator displaying connection status in the UI header.

Sync Recovery Queue

Offline user actions (e.g., task updates, login sessions) are captured and held in an offline recovery queue (stemmate_offline_queue).

When connection is restored, the application triggers a sync sweep to post queued items to local/remote storage and flush the queue without losing user data.

Data Persistence & Fallback

Dual-layer storage implementation utilizing both localStorage and IndexedDB.

Fallback mechanics to maintain user state and cached lessons when operating completely offline in remote Namibian regions.

Zero-Dependency Single-File Delivery

High-performance single HTML bundle incorporating inline Tailwind CSS (via CDN) and vanilla JS logic for low bandwidth environments.

 Repository Structure

STEMMate-Namibia/
├── README.md         # Setup and architectural documentation (Task 12)
└── index.html        # Complete production vertical slice bundle (Tasks 10–12)


Setup & Local Execution Guide

Since the vertical slice is designed to be lightweight and zero-dependency, running it locally requires no complex build tools or npm install steps.

Prerequisites

Any modern web browser (Google Chrome, Microsoft Edge, Mozilla Firefox, Safari).

Git (for cloning the repository).

Step-by-Step Launch

Clone the Repository

git clone https://github.com/YOUR_GITHUB_USERNAME/STEMMate-Namibia.git
cd STEMMate-Namibia


Open the Application

Option A (Direct File Launch): Double-click index.html inside your project directory to open it directly in your browser.

Option B (VS Code Live Server - Recommended): Open the folder in VS Code, right-click index.html, and select Open with Live Server.

🧪 Testing Sync Recovery (Task 12 Verification)

To test and verify the sync recovery mechanics built for Task 12:

Launch the app and log in or interact with the dashboard.

Simulate Offline Mode:

Open Browser Developer Tools (F12 or Ctrl + Shift + I).

Go to the Network tab.

Change the throttling dropdown from No throttling to Offline.

Observe the UI status badge update to Offline.

Perform Actions while Offline:

Create or update tasks/sessions.

Verify that items are added to the offline sync queue shown in the UI debug/logs pane.

Simulate Network Restoration:

Change the throttling dropdown back to No throttling (or Online).

Observe the status badge change to Online and the automatic sync recovery process empty the queue and persist the synced state.

Commit & Branching Strategy

Main Branch: main (Production release branch)

Feature Branch: feature/naobeb-tasks-10-12 (Task development and sync recovery implementation)

Authors & Acknowledgments

Naobeb — Lead Developer for Vertical Slice (Tasks 10, 11, and 12)

STEMMate Team Namibia — Architecture & Requirements Integration
