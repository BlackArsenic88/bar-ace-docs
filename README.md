# Bar Ace - Cross-Platform UBE Exam Prep Engine

[![Build Status](https://img.shields.io/badge/build-passing-brightgreen.svg)](#cicd-deployment-architecture)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.x-blue.svg)](https://www.typescriptlang.org/)
[![Framework](https://img.shields.io/badge/Framework-React%20Native%20%2F%20Expo-000000.svg)](https://expo.dev/)
[![License](https://img.shields.io/badge/License-Proprietary-red.svg)](#license)

Bar Ace is an enterprise-grade, offline-first cross-platform mobile application designed to deliver full-spectrum preparation for the **Uniform Bar Examination (UBE)**. Built using React Native, Expo, and WatermelonDB/SQLite, it provides an intuitive, high-performance environment for mastering the Multistate Bar Examination (MBE), Multistate Essay Examination (MEE), Multistate Performance Test (MPT), and Black Letter Law rules.

---

## Table of Contents
- [Architecture & Tech Stack](#architecture--tech-stack)
- [Key Features](#key-features)
- [Project Structure](#project-structure)
- [Prerequisites & Environment Setup](#prerequisites--environment-setup)
- [Installation](#installation)
- [Development Workflow](#development-workflow)
- [Testing Strategy](#testing-strategy)
- [Deployment & OTA Updates](#deployment--ota-updates)
- [License](#license)

---

## Architecture & Tech Stack

```
┌─────────────────────────────────────────────────────────────────┐
│                       REACT NATIVE / EXPO                       │
├────────────────────────────────┬────────────────────────────────┤
│  State & Sync Management       │  Local Database                │
│  • Redux Toolkit / Zustand     │  • WatermelonDB / SQLite       │
│  • TanStack Query (React Query)│  • MMKV (Key-Value Cache)       │
├────────────────────────────────┴────────────────────────────────┤
│  TypeScript 5.x (Strict Mode)                                   │
└─────────────────────────────────────────────────────────────────┘
```

* **Core Framework:** React Native managed via Expo SDK.
* **Language:** TypeScript 5.x (`strict: true`).
* **State & Data Synchronization:**
  * **Global State:** Zustand / Redux Toolkit with persistent state offline queues.
  * **Server State & Caching:** TanStack Query (React Query) with persistent storage wrappers.
  * **Local Database:** WatermelonDB / SQLite for relational data (questions, attempts, decks).
  * **Key-Value Cache:** `react-native-mmkv` for high-speed UI preference and session storage.
* **Styling & UI:** NativeWind (Tailwind CSS for React Native) adhering to Apple HIG and Material Design 3 guidelines.

---

## Key Features

1. **MBE Testing Engine:** 200 multiple-choice questions across 7 core legal subjects. Supports real-time practice feedback and timed examination modes.
2. **MEE & MPT Split Workspaces:** Rich-text draft editors with auto-saving every 3 seconds, integrated issue checklists, model answers, and split-screen document readers (File & Library).
3. **Black Letter Law Engine & SRS Flashcards:** Comprehensive searchable database of legal rules. Integrates SuperMemo-2 (SM-2) algorithm logic to generate dynamic flashcard decks from incorrect quiz answers.
4. **Offline-First Synchronization:** Local-first architecture powered by delta-based background synchronization upon network restoration.
5. **Analytics & Performance Tracking:** Deep-dive dashboards measuring sub-topic precision, timing breakdown, and score trajectories.

---

## Project Structure

```text
bar-ace/
├── .github/              # GitHub Actions workflows for CI/CD
├── src/
│   ├── assets/           # Static media, fonts, and icons
│   ├── components/       # Shared UI components (Buttons, Cards, Inputs)
│   ├── database/         # WatermelonDB/SQLite schemas and migrations
│   ├── features/         # Feature modules
│   │   ├── flashcards/   # SRS deck generator and SuperMemo-2 algorithm
│   │   ├── mbe/          # MBE quiz engine and explanation drawers
│   │   ├── mee/          # MEE essay editor and self-grading rubrics
│   │   ├── mpt/          # MPT split workspace and PDF reader
│   │   └── rules/        # Searchable Black Letter Law rule engine
│   ├── hooks/            # Custom React hooks (Network, LocalStorage, Timers)
│   ├── navigation/       # React Navigation stack & tab definitions
│   ├── services/         # API clients, sync workers, and network queues
│   ├── store/            # Zustand/Redux global state and slices
│   ├── types/            # TypeScript interfaces and domain schemas
│   └── utils/            # Helper functions (Formatters, SRS calculations)
├── __tests__/            # Unit and integration test suites
├── app.json              # Expo configuration
├── eas.json              # Expo Application Services build configuration
├── package.json          # Project dependencies
└── tsconfig.json         # TypeScript strict configuration
```

---

## Prerequisites & Environment Setup

Ensure you have the following installed on your machine:
* **Node.js:** `v18.x` or `v20.x`
* **Package Manager:** `npm` (v9+) or `pnpm`
* **Expo CLI:** Installed globally or run via `npx expo`
* **iOS Development:** macOS with Xcode 15+ and CocoaPods
* **Android Development:** Android Studio with SDK level 34+ and configured emulator

---

## Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/barace/bar-ace-app.git
   cd bar-ace-app
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Configure Environment Variables:**
   Create a `.env` file in the root directory:
   ```env
   EXPO_PUBLIC_API_BASE_URL=https://api.barace.app/v1
   EXPO_PUBLIC_ENABLE_ANALYTICS=true
   ```

---

## Development Workflow

Start the metro bundler:

```bash
# Start Expo Metro Bundler
npm run start

# Launch on iOS Simulator
npm run ios

# Launch on Android Emulator
npm run android
```

---

## Testing Strategy

Bar Ace enforces high test coverage ($\ge 85\%$) across core domain engines (scoring, timing, spaced repetition, sync).

```bash
# Run unit tests for engines and utility calculations
npm run test:unit

# Run integration tests with coverage report
npm run test:unit -- --coverage

# Run database and local persistence tests
npm run test:integration
```

---

## Deployment & OTA Updates

Builds are executed and distributed via Expo Application Services (EAS).

### Generating Beta Preview Builds

```bash
# Build iOS Preview for TestFlight
eas build --platform ios --profile preview --auto-submit

# Build Android App Bundle (AAB) for Google Play Beta
eas build --platform android --profile preview --auto-submit
```

### Deploying Over-The-Air (OTA) Content Patches

For rapid bug fixes or legal rule citation corrections without app store re-review:

```bash
eas update --branch production --message "Update Contracts rule citation #104"
```

---

## License

Copyright © 2026 Bar Ace Inc. All rights reserved.  
Unlawful copying, distribution, or modifications of this software via any medium is strictly prohibited without explicit written consent from Bar Ace Inc.