# Grocery Collab App

A mobile-first collaborative grocery application for families, roommates, couples, and shared households.

## Product Goal

Grocery Collab App makes it easy for household members to add groceries as soon as they notice something is missing, running low, or wanted. The core list must remain fast and useful even when AI or retailer integrations are unavailable.

## Core Product Principles

- Adding an item is immediate; AI and retailer checks run asynchronously.
- Family and collaborative households use one flexible role and permission system.
- The app works with or without retailer integrations.
- AI enriches and suggests rather than silently overriding user intent.
- Household data and product preferences are protected at the backend/database layer.
- The architecture should support users in Jamaica, the United States, and markets without supported retailer APIs.

## Planned Tech Stack

### Client
- React Native
- Expo
- TypeScript
- Expo Router

### Backend
- Supabase
- PostgreSQL
- Supabase Auth
- PostgreSQL Row Level Security (RLS)
- Supabase Realtime
- Supabase Storage

### Mobile / Distribution
- Expo Application Services (EAS)
- TestFlight for iOS testing
- Google Play / Android testing tracks

### Later Integrations
- AI/vision service for item normalization, categorization, duplicate detection, preference resolution, and image interpretation
- Provider-neutral retailer availability service with regional adapters and no-integration fallback
- Push notifications
- Sentry or equivalent monitoring

## Roadmap

### Phase 0 — Project Foundation & UI Proof of Concept
Build the mobile navigation, grocery list, add-item flow, household selector, shopping mode, and mocked permission states.

### Phase 1 — Secure Functional Prototype
Add authentication, households, membership roles, invitations, grocery CRUD workflows, Row Level Security, and realtime collaboration.

### Phase 2 — Family Beta / Pilot
Create installable preview builds, improve resilient mobile UX, add notifications/history/monitoring, and test across real household shopping cycles.

### Phase 3 — Product Preferences & Smart Capture
Add saved household/member product preferences, product photos, camera capture, barcode scanning, and confirmation flows.

### Phase 4 — AI Item Intelligence
Add categorization, normalized item matching, duplicate suggestions, quantity parsing, preference phrases such as “Mom's oat milk,” and optional image interpretation.

### Phase 5 — Retailer Availability Service
Add preferred stores, asynchronous product availability checks, retailer adapters, caching, and graceful unsupported-store fallback.

### Phase 6 — Production Hardening & Public Release
Complete security, testing, CI/CD, privacy, monitoring, backup/recovery, rate limiting, accessibility, and app-store release preparation.

### Phase 7 — Future Intelligent Household Features
Explore running-low signals, reorder prediction, recipes, substitutions, price comparison, optimized shopping order, and voice integrations.

## Project Documentation

Detailed architecture, feature specifications, and phased implementation notes are maintained in Notion:

- [Grocery Collab App — Notion Project](https://app.notion.com/p/3e6e4a2ede2981a88494f15fc02afcc9)

## Current Status

Planning / project foundation.
