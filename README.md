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
- Meal planning should connect directly to grocery actions rather than becoming a separate disconnected feature.

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
- Recipe provider abstraction for meal search and structured ingredients
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

### Phase 4 — Meal-to-List & Serving Size
Add meal search, structured recipe ingredients, serving-size controls, deterministic ingredient scaling, ingredient selection, duplicate checking, and direct addition of selected ingredients to the household grocery list. Recipe-added items should retain the meal as their source and remain editable before confirmation.

### Phase 5 — AI Item Intelligence
Add categorization, normalized item matching, duplicate suggestions, quantity parsing, preference phrases such as “Mom's oat milk,” and optional image interpretation.

### Phase 6 — Retailer Availability Service
Add preferred stores, asynchronous product availability checks, retailer adapters, caching, and graceful unsupported-store fallback.

### Phase 7 — Production Hardening & Public Release
Complete security, testing, CI/CD, privacy, monitoring, backup/recovery, rate limiting, accessibility, and app-store release preparation.

### Phase 8 — Future Intelligent Household Features
Explore running-low signals, reorder prediction, saved recipes, recipe URL import, weekly meal planning, pantry-aware “What can we make?” suggestions, AI recipe generation, substitutions, price comparison, optimized shopping order, and voice integrations.

## Meal-to-List Feature

A user should be able to search for a meal such as **Chicken Alfredo**, choose a recipe, change the serving count, and add selected ingredients directly to the grocery list.

Example serving scaling:

- Chicken breast: 2 → 4
- Fettuccine: 250 g → 500 g
- Heavy cream: 1 cup → 2 cups

The feature should:

- Keep the recipe's original serving count.
- Scale numeric ingredient quantities using the selected serving size.
- Preserve non-numeric quantities such as `salt to taste` without inventing a value.
- Let users deselect ingredients they already have.
- Compare ingredients with the current grocery list before adding them.
- Reuse the normal grocery normalization and duplicate-resolution flow.
- Store enough source metadata to show which meal added an ingredient.
- Allow users to review and edit the resulting quantities before final confirmation.

Detailed implementation notes are maintained on the linked Notion feature page.

## Project Documentation

Detailed architecture, feature specifications, and phased implementation notes are maintained in Notion:

- [Grocery Collab App — Notion Project](https://app.notion.com/p/3e6e4a2ede2981a88494f15fc02afcc9)
- [Meal-to-List & Serving Size — Notion Feature](https://app.notion.com/p/3e6e4a2ede2981dc8553ffd76603b5e5)

## Current Status

Planning / project foundation.