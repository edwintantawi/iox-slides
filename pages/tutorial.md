---
layout: fact
---

# <span class="firebase-text">Let's Dive In</span>

---
layout: statement
transition: view-transition
---

<style>
  .title-firebase {
    view-transition-name: title-firebase;
  }
</style>

# Add <span class="title-firebase firebase-text">Firebase</span> <br/> To Your <span class="flutter-text">Flutter</span> App

---
layout: statement
transition: view-transition
---

# Sign into <span class="title-firebase firebase-text">Firebase</span> using your Google account.

<p class="pt-4 text-slate"><a href="https://console.firebase.google.com">console.firebase.google.com</a></p>

---
layout: default
---

# Install <span class="firebase-text">Firebase</span> CLI

<v-clicks>

- If you haven't already, [install the Firebase CLI](https://firebase.google.com/docs/cli#setup_update_cli).
- Log into Firebase using your Google account
  ```bash
  $ firebase login
  > sign in to your firebase account
  ```
- Install the FlutterFire CLI

  ```bash
  $ dart pub global activate flutterfire_cli
  ```

</v-clicks>

---
layout: default
---

# Configure Your Apps To Use <span class="firebase-text">Firebase</span>

<v-clicks depth="2">

- Configure your apps to use Firebase
  ```bash
  flutter-app$ flutterfire configure
  ```
  - Asks you to select the platforms ( iOS, Android, Web )
  - You can select either to use an existing Firebase project or to create a new Firebase project
  - Creates a Firebase configuration file (`firebase_options.dart`)

</v-clicks>

---
layout: default
---

# Initialize <span class="firebase-text">Firebase</span> In Your App

<v-clicks>

- Install the core plugin
  ```bash
  flutter-app$ flutter pub add firebase_core
  ```
- Ensure that your Flutter app's Firebase configuration is up-to-date
  ```bash
  flutter-app$ flutterfire configure
  ```
- Import the Firebase core plugin and the configuration
  ```dart
  import 'package:firebase_core/firebase_core.dart';
  import 'firebase_options.dart';
  ```
- Initialize Firebase using the `DefaultFirebaseOptions` from the configuration file
  ```dart
  await Firebase.initializeApp(
    options: DefaultFirebaseOptions.currentPlatform,
  );
  ```
- Run your Flutter app
  ```bash
  flutter-app$ flutter run
  ```

</v-clicks>

---
layout: default
---

## main.dart

````md magic-move {lines: true}
```dart
import 'package:flutter/material.dart';
import 'package:myapp/screens/home_screen.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(/**... */)
  }
}

```

```dart {*|2,7|1,8-10|*}
import 'package:firebase_core/firebase_core.dart';
import 'package:flutter/material.dart';
import 'package:myapp/firebase_options.dart';
import 'package:myapp/screens/home_screen.dart';

Future<void> main() async {
  WidgetsFlutterBinding.ensureInitialized();
  await Firebase.initializeApp(
    options: DefaultFirebaseOptions.currentPlatform,
  );

  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(/**... */)
  }
}
```
````

---
layout: default
transition: view-transition
---

# Add <span class="title-firebase firebase-text">Firebase</span> Plugins

<v-clicks>

- Add/Install Firebase plugin
  ```bash
  flutter-app$ flutter pub add PLUGIN_NAME
  ```
  ```dart
  [firebase_analytics, firebase_auth, cloud_firestore, firebase_storage, ..., firebase_vertexai]
  ```
- Ensures that your Flutter app's Firebase configuration is up-to-date
  ```bash
  flutter-app$ flutterfire configure
  ```

</v-clicks>

---
layout: statement
---

# Get started with the <span class="gemini-text">Gemini API</span> using the <span class="vertex-ai-text">Vertex AI</span> for <span class="title-firebase firebase-text">Firebase</span>

---
layout: default
---

# <span class="firebase-text">Prerequisites</span>

<v-clicks depth="2">

- Make sure that your development environment: `Dart 3.2.0+`
- Upgrade your project to use the [Blaze pay-as-you-go pricing plan](https://console.firebase.google.com/project/_/overview?purchaseBillingPlan=metered)
- Enable the following two APIs for your project:
  - `aiplatform.googleapis.com`
  - `firebaseml.googleapis.com`
- Add the Flutter Firebase Vertex AI plugin:
  ```bash
  flutter-app$ flutter pub add firebase_vertexai
  ```

</v-clicks>
