# Budget Calculator

A personal budget tracker built with Flutter that runs on Android, iOS and the web from one codebase. Users sign in, record their income and expenses, and see what is left of their budget in real time. Data is stored per user in Cloud Firestore.

<!--
Screenshots: add the web dashboard and the mobile view side by side, for example:
<p float="left">
  <img src="screenshots/web.png" width="480" />
  <img src="screenshots/mobile.png" width="220" />
</p>
-->

## Features

- Sign in with email and password, or with Google (popup flow on web, native flow on mobile)
- Add income and expense entries with a name and amount
- Running totals for income, expenses and remaining budget
- Entries stored in `incomes` and `expenses` subcollections under each user's Firestore document
- Responsive layout: a dedicated web layout for wide screens and a mobile layout for phones, chosen at runtime

## Tech stack

| Area | Tools |
|---|---|
| UI | Flutter (mobile and web), Google Fonts, flutter_svg |
| State management | hooks_riverpod with flutter_hooks |
| Backend | Firebase Authentication, Cloud Firestore |
| Sign-in | google_sign_in, sign_button |

## Project structure

```
lib/
├── main.dart               # Firebase init and app entry
├── responsive_handler.dart # picks the web or mobile layout by screen width
├── view_model.dart         # auth, Firestore reads and writes, budget totals (Riverpod)
├── models.dart             # income and expense entry model
├── components.dart         # shared widgets
├── mobile/                 # login and expense screens for phones
└── web/                    # login and expense screens for wide screens
```

## Getting started

1. Clone the repository and install packages:
   ```sh
   git clone https://github.com/mosabmoammar/budget_app_flutter_lu.git
   cd budget_app_flutter_lu
   flutter pub get
   ```
2. Create a Firebase project, enable Email/Password and Google sign-in, and create a Firestore database.
3. Connect the app to your project with the FlutterFire CLI (this regenerates `lib/firebase_options.dart`):
   ```sh
   flutterfire configure
   ```
4. Run it on a device or in Chrome:
   ```sh
   flutter run
   flutter run -d chrome
   ```
