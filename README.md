# JUNG Mobile

A cross-platform mobile application built with [Expo](https://expo.dev) and React Native. Features file-based routing, Tailwind-style styling via NativeWind, Supabase for backend services, and EAS Build for streamlined CI/CD.

## Tech Stack

| Layer | Technology |
|---|---|
| Framework | React Native + Expo 52 |
| Navigation | Expo Router (file-based) |
| Styling | NativeWind (Tailwind CSS) |
| State | Zustand |
| Backend / Auth | Supabase |
| Builds | EAS Build |
| Language | TypeScript |

## Prerequisites

- [Node.js](https://nodejs.org) 18+
- [Expo CLI](https://docs.expo.dev/more/expo-cli/) — `npm install -g expo-cli`
- [EAS CLI](https://docs.expo.dev/eas/) — `npm install -g eas-cli` *(for device builds)*
- A [Supabase](https://supabase.com) project

## Getting Started

**1. Install dependencies**

```bash
npm install
```

**2. Configure environment variables**

Create a `.env.local` file at the project root:

```env
EXPO_PUBLIC_SUPABASE_URL=your_supabase_project_url
EXPO_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
```

**3. Start the development server**

```bash
npm start
```

Then press `a` for Android, `i` for iOS, or `w` for web in the Expo CLI prompt.

> [!NOTE]
> The `npm start` command uses the Expo Dev Client. Make sure you have the Expo Go app or a custom dev client installed on your device.

## Running on a Device or Emulator

```bash
# Android emulator
npm run android

# iOS simulator (macOS only)
npm run ios

# Web browser
npm run web
```

## Project Structure

```
app/
├── _layout.tsx          # Root stack navigator
└── (tabs)/
    ├── _layout.tsx      # Tab bar configuration
    ├── index.tsx        # Home screen
    ├── list.tsx         # List screen
    └── details.tsx      # Details screen
components/              # Shared UI components
store/
└── store.ts             # Zustand global store
utils/
└── supabase.ts          # Supabase client setup
```

## Building for Distribution

Builds are managed via [EAS Build](https://docs.expo.dev/build/introduction/).

```bash
# Development build (internal distribution)
npm run build:dev

# Preview build (internal distribution)
npm run build:preview

# Production build (app stores)
npm run build:prod
```

> [!TIP]
> Run `eas login` and `eas build:configure` before your first EAS build.

## Code Quality

```bash
# Lint and format check
npm run lint

# Auto-fix lint and formatting
npm run format
```
