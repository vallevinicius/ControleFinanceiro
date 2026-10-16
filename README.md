<div align="center">

# Your Money, Your Life

**Personal finance tracker with Firebase authentication, Firestore and interactive charts.**

🇧🇷 [Leia em português](README.pt-BR.md)

[![CI](https://github.com/vallevinicius/ControleFinanceiro/actions/workflows/firebase-hosting-pull-request.yml/badge.svg)](https://github.com/vallevinicius/ControleFinanceiro/actions/workflows/firebase-hosting-pull-request.yml) ![JavaScript](https://img.shields.io/badge/JavaScript-ES6-F7DF1E?logo=javascript&logoColor=white) ![Firebase](https://img.shields.io/badge/Firebase--FFCA28?logo=firebase&logoColor=white) ![Chart.js](https://img.shields.io/badge/Chart.js--FF6384?logo=chartdotjs&logoColor=white)

</div>

## About

Responsive web app to record income and expenses and analyse them by month or year. Built with plain JavaScript modules (no framework) on top of Firebase Authentication and Cloud Firestore, deployed on Firebase Hosting.

## Features

- Sign-up, login and password recovery (Firebase Auth)
- Transactions stored per user in Firestore, synced across devices
- Dashboard with balance, history and monthly/yearly views
- Per-category dashboards with column, bar, line and pie charts
- Responsive layout with collapsible sidebar and custom modals

## Tech stack

| Layer | Technology |
|---|---|
| Front-end | HTML5, CSS3, JavaScript (ES modules) |
| Backend | Firebase Authentication, Cloud Firestore, Firebase Hosting |
| Charts | Chart.js |
| CI | GitHub Actions → Firebase Hosting preview on every PR |

## Security

- Firestore rules (`firestore.rules`) only allow a signed-in user to read or change transactions whose `uid` is their own
- The Firebase web config in `public/main.js` is public by design; access control lives in the security rules

## Getting started

**Prerequisites:** a Firebase project with Authentication (e-mail/password) and Firestore, Firebase CLI

```bash
npm install -g firebase-tools
firebase login
# put your project's firebaseConfig at the top of public/main.js
firebase emulators:start      # or: firebase serve
firebase deploy               # rules, indexes and hosting
```
The composite indexes the dashboards need are declared in `firestore.indexes.json` and are created by `firebase deploy`.

## Team

- [Vinicius do Valle](https://github.com/vallevinicius)
