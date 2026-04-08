# Uber Clone

A full-featured Uber-clone mobile application built with React Native and Expo, covering ride booking, live maps, payments, and ride history.

## Features

### Authentication
- Email/password sign-up and sign-in via Clerk
- One-time passcode (OTP) verification
- Google OAuth sign-in

### Home Screen
- GPS location detection on launch
- Reverse geocoding to display the user's current address
- Live map showing nearby driver markers

### Ride Booking
- Google Places Autocomplete for destination search
- Route calculation with the Google Directions API
- Per-driver ETA and price estimate before booking

### Payment
- Full Stripe integration — creates a `PaymentIntent` server-side and presents the native payment sheet
- Payment confirmed before ride is saved

### Ride History
- Past rides fetched from a NeonDB serverless Postgres database via API routes

## Tech Stack

| Category | Technology |
|---|---|
| Framework | Expo 51, React Native |
| Language | TypeScript |
| Navigation | Expo Router (file-based) |
| Authentication | Clerk (email, OTP, Google OAuth) |
| Database | NeonDB (serverless Postgres) |
| Payments | Stripe (PaymentIntent + payment sheet) |
| Maps | Google Maps SDK, Directions API, Places API |
| Styling | NativeWind (Tailwind CSS for RN) |
| State management | Zustand |

## Project Structure

```
app/
├── (auth)/            # Login, sign-up, and OTP screens
└── (root)/
    ├── (tabs)/        # Home, ride history, and profile tabs
    └── (api)/         # Server-side API routes (NeonDB, Stripe)

components/            # Reusable UI components (map, driver card, etc.)
lib/                   # Utility functions and API helpers
store/                 # Zustand state stores
```

## Getting Started

### Prerequisites

- Node.js 18+
- Expo CLI (`npm install -g expo-cli`)
- Accounts and API keys for: Clerk, Stripe, NeonDB, Google Cloud (Maps, Directions, Places)

### Installation

```bash
npm install
```

### Environment Variables

Create a `.env` file at the project root:

```env
EXPO_PUBLIC_CLERK_PUBLISHABLE_KEY=...
EXPO_PUBLIC_GOOGLE_API_KEY=...
EXPO_PUBLIC_STRIPE_PUBLISHABLE_KEY=...
STRIPE_SECRET_KEY=...
DATABASE_URL=...
```

### Run

```bash
npx expo start
```

Open in the iOS Simulator, Android emulator, or Expo Go.
