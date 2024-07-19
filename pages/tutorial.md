---
layout: image
image: "/cat-loading.jpg"
---

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

```dart {1,6-7}
import 'package:firebase_core/firebase_core.dart';
import 'package:flutter/material.dart';
import 'package:myapp/screens/home_screen.dart';

Future<void> main() async {
  WidgetsFlutterBinding.ensureInitialized();
  await Firebase.initializeApp();

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

```dart {3,9|8-10|*}
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
  - [aiplatform.googleapis.com](https://console.cloud.google.com/apis/library/aiplatform.googleapis.com?project=_)
  - [firebaseml.googleapis.com](https://console.cloud.google.com/apis/library/firebaseml.googleapis.com?project=_)
- Add the Flutter Firebase Vertex AI plugin:
  ```bash
  flutter-app$ flutter pub add firebase_vertexai
  ```
- Enable Vertex AI for Firebase on Firebase console

</v-clicks>

---
layout: default
---

# Initialize The <span class="vertex-ai-text">Vertex AI</span> Service And The <span class="gemini-text">Model</span>

````md magic-move {lines: true}
```dart {1|1,3}
import 'package:firebase_vertexai/firebase_vertexai.dart';

final model = FirebaseVertexAI.instance.generativeModel();
```

```dart {4|*}
import 'package:firebase_vertexai/firebase_vertexai.dart';

final model = FirebaseVertexAI.instance.generativeModel(
  model: 'gemini-1.5-flash'
);
```
````

---
layout: default
---

# <span class="gemini-text">Generate</span> Text From Text-Only Prompts

````md magic-move {lines: true}
```dart {1|1,3}
import 'package:firebase_vertexai/firebase_vertexai.dart';

final prompt = [Content.text()]

```

```dart {3-5}
import 'package:firebase_vertexai/firebase_vertexai.dart';

final prompt = [
  Content.text("Recommendations for places that must be visited in Medan")
]
```

```dart {3-5}
import 'package:firebase_vertexai/firebase_vertexai.dart';

final prompt = [
  Content.text(inputController.text)
]
```

```dart {2,8}
import 'package:firebase_vertexai/firebase_vertexai.dart';
import 'package:myapp/model.dart';

final prompt = [
  Content.text(inputController.text)
]

final response = await model.generateContent();
```

```dart {4-6,8-10}
import 'package:firebase_vertexai/firebase_vertexai.dart';
import 'package:myapp/model.dart';

final prompt = [
  Content.text(inputController.text)
]

final response = await model.generateContent(
  prompt
);
```

```dart {8-10,12|5,12-13|*}
import 'package:firebase_vertexai/firebase_vertexai.dart';
import 'package:myapp/model.dart';

final prompt = [
  Content.text("Recommendations for places that must be visited in Medan")
]

final response = await model.generateContent(
  prompt
);

print(response.text)
// Output: Must-Visit Places in Medan:\nFor Cultural Immersions:\n\n-Maimun Palace: Witness the grandeur of Med...
```
````

---
layout: default
---

# Generate Text From <span class="gemini-text">Multimodal</span> Prompts

````md magic-move {lines: true}
```dart {3,6|1,8|3,8-9}
import 'dart:io';

import 'package:firebase_vertexai/firebase_vertexai.dart';
import 'package:myapp/model.dart';

final prompt = TextPart("What's in the picture?");

final image = await File('image-somewhere.jpg').readAsBytes();
final imagePart = DataPart('image/jpeg', image);
```

```dart {4,11}
import 'dart:io';

import 'package:firebase_vertexai/firebase_vertexai.dart';
import 'package:myapp/model.dart';

final prompt = TextPart("What's in the picture?");

final image = await File('image-somewhere.jpg').readAsBytes();
final imagePart = DataPart('image/jpeg', image);

final response = await model.generateContent();
```

```dart {12}
import 'dart:io';

import 'package:firebase_vertexai/firebase_vertexai.dart';
import 'package:myapp/model.dart';

final prompt = TextPart("What's in the picture?");

final image = await File('image-somewhere.jpg').readAsBytes();
final imagePart = DataPart('image/jpeg', image);

final response = await model.generateContent(
  [Content.multi()]
);
```

```dart {6,9,12|11-13}
import 'dart:io';

import 'package:firebase_vertexai/firebase_vertexai.dart';
import 'package:myapp/model.dart';

final prompt = TextPart("What's in the picture?");

final image = await File('image-somewhere.jpg').readAsBytes();
final imagePart = DataPart('image/jpeg', image);

final response = await model.generateContent(
  [Content.multi([prompt, imagePart])]
);
```

```dart {11-13,15|*}
import 'dart:io';

import 'package:firebase_vertexai/firebase_vertexai.dart';
import 'package:myapp/model.dart';

final prompt = TextPart("What's in the picture?");

final image = await File('image-somewhere.jpg').readAsBytes();
final imagePart = DataPart('image/jpeg', image);

final response = await model.generateContent(
  [Content.multi([prompt, imagePart])]
);

print(response.text);
```

```dart {10-11}
import 'dart:io';

import 'package:firebase_vertexai/firebase_vertexai.dart';
import 'package:myapp/model.dart';

final prompt = TextPart("What's in the picture?");

final image = await File('image-somewhere.jpg').readAsBytes();
final imagePart = DataPart('image/jpeg', image);
// Want to add multiple image, no problem...
final imagePart2 = DataPart('image/jpeg', otherImageFromeSomeWhere);

final response = await model.generateContent(
  [Content.multi([prompt, imagePart])]
);

print(response.text);
```

```dart {11,14}
import 'dart:io';

import 'package:firebase_vertexai/firebase_vertexai.dart';
import 'package:myapp/model.dart';

final prompt = TextPart("What's in the picture?");

final image = await File('image-somewhere.jpg').readAsBytes();
final imagePart = DataPart('image/jpeg', image);
// Want to add multiple images, no problem...
final imagePart2 = DataPart('image/jpeg', otherImageFromeSomeWhere);

final response = await model.generateContent(
  [Content.multi([prompt, imagePart, imagePart2])]
);

print(response.text);
```

```dart {6|6,13-15,17|*}
import 'dart:io';

import 'package:firebase_vertexai/firebase_vertexai.dart';
import 'package:myapp/model.dart';

final prompt = TextPart("What's different between these pictures?");

final image = await File('image-somewhere.jpg').readAsBytes();
final imagePart = DataPart('image/jpeg', image);
// Want to add multiple images?, no problem...
final imagePart2 = DataPart('image/jpeg', otherImageFromeSomeWhere);

final response = await model.generateContent(
  [Content.multi([prompt, imagePart, imagePart2])]
);

print(response.text);
```

```dart {11-12}
import 'dart:io';

import 'package:firebase_vertexai/firebase_vertexai.dart';
import 'package:myapp/model.dart';

final prompt = TextPart("What's different between these pictures?");

final image = await File('image-somewhere.jpg').readAsBytes();
final imagePart = DataPart('image/jpeg', image);
final imagePart2 = DataPart('image/jpeg', otherImageFromeSomeWhere);
// Want to add other file format?, no problem...
// Supported input files varies by model and can include images, PDFs, video, and audio

final response = await model.generateContent(
  [Content.multi([prompt, imagePart, imagePart2])]
);

print(response.text);
```

```dart {11-14}
import 'dart:io';

import 'package:firebase_vertexai/firebase_vertexai.dart';
import 'package:myapp/model.dart';

final prompt = TextPart("What's different between these pictures?");

final image = await File('image-somewhere.jpg').readAsBytes();
final imagePart = DataPart('image/jpeg', image);
final imagePart2 = DataPart('image/jpeg', otherImageFromeSomeWhere);
// Want to add other file format?, no problem...
// Supported input files varies by model and can include images, PDFs, video, and audio
final video = await File('video.mp4').readAsBytes();
final videoPart = DataPart('video/mp4', video);

final response = await model.generateContent(
  [Content.multi([prompt, imagePart, imagePart2])]
);

print(response.text);
```

```dart {11-14,17}
import 'dart:io';

import 'package:firebase_vertexai/firebase_vertexai.dart';
import 'package:myapp/model.dart';

final prompt = TextPart("What's different between these pictures?");

final image = await File('image-somewhere.jpg').readAsBytes();
final imagePart = DataPart('image/jpeg', image);
final imagePart2 = DataPart('image/jpeg', otherImageFromeSomeWhere);
// Want to add other file format?, no problem...
// Supported input files varies by model and can include images, PDFs, video, and audio
final video = await File('video.mp4').readAsBytes();
final videoPart = DataPart('video/mp4', video);

final response = await model.generateContent(
  [Content.multi([prompt, videoPart])]
);

print(response.text);
```

```dart {6,11-14,17}
import 'dart:io';

import 'package:firebase_vertexai/firebase_vertexai.dart';
import 'package:myapp/model.dart';

final prompt = TextPart("What's in the video?");

final image = await File('image-somewhere.jpg').readAsBytes();
final imagePart = DataPart('image/jpeg', image);
final imagePart2 = DataPart('image/jpeg', otherImageFromeSomeWhere);
// Want to add other file format?, no problem...
// Supported input files varies by model and can include images, PDFs, video, and audio
final video = await File('video.mp4').readAsBytes();
final videoPart = DataPart('video/mp4', video);

final response = await model.generateContent(
  [Content.multi([prompt, videoPart])]
);

print(response.text);
```

```dart {10}
import 'dart:io';

import 'package:firebase_vertexai/firebase_vertexai.dart';
import 'package:myapp/model.dart';

final prompt = TextPart("What's in the video?");

final video = await File('video.mp4').readAsBytes();
final videoPart = DataPart('video/mp4', video);
// For Vertex AI for Firebase SDKs, the maximum request size is 20 MB

final response = await model.generateContent(
  [Content.multi([prompt, videoPart])]
);

print(response.text);
```

```dart {10-13}
import 'dart:io';

import 'package:firebase_vertexai/firebase_vertexai.dart';
import 'package:myapp/model.dart';

final prompt = TextPart("What's in the video?");

final video = await File('video.mp4').readAsBytes();
final videoPart = DataPart('video/mp4', video);
// For Vertex AI for Firebase SDKs, the maximum request size is 20 MB
// SOLUTION: Use a Cloud Storage for Firebase URL to include the file in your multimodal request.
final storageUrl = 'gs://$bucket/$fullPath';
final videoFromStoragePart = FileData('video/mp4', storageUrl);

final response = await model.generateContent(
  [Content.multi([prompt, videoPart])]
);

print(response.text);
```

```dart {10-13,16}
import 'dart:io';

import 'package:firebase_vertexai/firebase_vertexai.dart';
import 'package:myapp/model.dart';

final prompt = TextPart("What's in the video?");

final video = await File('video.mp4').readAsBytes();
final videoPart = DataPart('video/mp4', video);
// For Vertex AI for Firebase SDKs, the maximum request size is 20 MB
// SOLUTION: Use a Cloud Storage for Firebase URL to include the file in your multimodal request.
final storageUrl = 'gs://$bucket/$fullPath';
final videoFromStoragePart = FileData('video/mp4', storageUrl);

final response = await model.generateContent(
  [Content.multi([prompt, videoFromStoragePart])]
);

print(response.text);
```

```dart
import 'dart:io';

import 'package:firebase_vertexai/firebase_vertexai.dart';
import 'package:myapp/model.dart';

final prompt = TextPart("What's in the video?");

final storageUrl = 'gs://$bucket/$fullPath';
final videoFromStoragePart = FileData('video/mp4', storageUrl);

final response = await model.generateContent(
  [Content.multi([prompt, videoFromStoragePart])]
);

print(response.text);
```
````

---
layout: default
---

# <span class="gemini-text">Streaming</span> The Results

````md magic-move {lines: true}
```dart {*}
import 'package:firebase_vertexai/firebase_vertexai.dart';
import 'package:myapp/model.dart';

final prompt = [
  Content.text("Recommendations for places that must be visited in Medan")
]

final response = await model.generateContent(
  prompt
);

print(response.text)
```

```dart {8}
import 'package:firebase_vertexai/firebase_vertexai.dart';
import 'package:myapp/model.dart';

final prompt = [
  Content.text("Recommendations for places that must be visited in Medan")
]

final response = await model.generateContentStream(
  prompt
);

print(response.text)
```

```dart {12-14|11}
import 'package:firebase_vertexai/firebase_vertexai.dart';
import 'package:myapp/model.dart';

final prompt = [
  Content.text("Recommendations for places that must be visited in Medan")
]

final response = await model.generateContentStream(
  prompt
);

await for (final chunk in response) {
  print(chunk.text);
}
```
````

---
layout: section
---

# Build <span class="firebase-text">Multi-Turn Conversations</span> (Chat) With The <span class="gemini-text">Gemini API</span>

<p class="pt-4 text-slate"><a href="https://firebase.google.com/docs/vertex-ai/chat?platform=flutter">firebase.google.com/docs/vertex-ai/chat</a></p>
