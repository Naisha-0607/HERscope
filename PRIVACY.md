# Privacy and data handling

## Current prototype behavior

HERscope is a browser-only prototype. The current app stores health journal entries, period dates, profile preferences, and a demo profile in browser `localStorage`. The demo account is **not** authentication and does not create an online account. No server-side storage or cloud sync is implemented.

## What that means

- Data may remain on the device/browser profile after the tab closes.
- Anyone with access to that same browser profile may be able to access the app's stored data. Do not use this prototype to store information you cannot risk exposing on a shared device.
- Clearing browser site data can erase entries. Private/incognito sessions may discard data when closed.
- Exported JSON reports may contain sensitive information. Store and share them carefully, and delete copies you no longer need.
- Browser-local storage is not encrypted by this application and should not be described as a secure medical record system.
- The app is educational and does not diagnose, confirm ovulation, calculate an individual's pregnancy probability, or replace professional care.

## Before production

A production release needs a documented threat model, a reviewed delete-all flow that removes every HERscope storage key, validated import/export, dependency and security review, accessible consent and privacy notices, and a decision on whether a backend is necessary. If a backend is added, authentication, authorisation, encryption in transit and at rest, retention/deletion policies, incident response, and applicable legal requirements must be designed and reviewed before collecting real health data.

## Data minimisation

Use synthetic data for demos and screenshots. Never commit real health records, exported JSON files, passwords, API keys, or personal identifiers to Git.
