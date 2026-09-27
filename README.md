# Byte Cloud Lab

A mobile-first Kubernetes learning app with Byte, covering Kubernetes, AKS, EKS and GKE through guided simulations and practical exercises.

Start with six guided incident labs: understand the evidence, edit settings or YAML, apply a repair, and verify a request. Animated Byte reactions, device narration, controller/Pod transitions and a Pod replacement experiment make feedback visible. The complete existing learning path and YAML/Helm reference workbench remain accessible.

The static website lives in `dist/`. Native Android and iOS project sources live in `mobile/`; see `mobile/RELEASE.md` for build instructions and remaining store-release work. No signed mobile binary has been produced.

Progress is local to the device. Examples are bounded simulations, not live Kubernetes or cloud commands. Six starter labs use the new touch controls; advanced lessons retain their existing workbench format.

## Run locally

Use Node.js 22.12 or newer.

```sh
npm ci
npm run dev
```

Open the URL printed by Vite. The ready-to-serve web app is in `dist/`.

For Android and iOS setup, see [mobile/RELEASE.md](mobile/RELEASE.md).

## Project layout

- `dist/`: web application, Byte artwork and bundled lessons
- `content/`: multilingual explanations, interview scenarios and animation definitions
- `mobile/`: Capacitor Android and iOS projects
- `scripts/`: content and asset generation utilities
- `tests/`: learning-flow and content verification

## Checks

- `node tests/mobile-practice.cjs` — all six lab repair/test flows, invalid drafts, cancellation and curriculum access.
- `node tests/ui-flow.cjs` — existing mission/command/YAML flow and progress migration.
- `node tests/animation-voice.cjs` — mocked narration, cluster transitions and request outcomes.
- `node tests/verify.cjs` and `node tests/packages.cjs` — YAML validation and Helm/Kustomize exercise checks.

Actual browser visual QA, mobile device installation and native audio playback have not been performed.
