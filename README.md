<!--
This README describes the package. If you publish this package to pub.dev,
this README's contents appear on the landing page for your package.

For information about how to write a good package README, see the guide for
[writing package pages](https://dart.dev/guides/libraries/writing-package-pages).

For general information about developing packages, see the Dart guide for
[creating packages](https://dart.dev/guides/libraries/create-library-packages)
and the Flutter guide for
[developing packages and plugins](https://flutter.dev/developing-packages).
-->

## Features

In your pubspec.yaml
```dart
dependencies:
  firebase_utilitas: ^latest-version
```

## Usage

calling first class
```dart
final fs = FirebaseUtilitas();
```

## Firestore

### add
```dart
await fs.addDataCollection("collection_name", {
"name": "ucup",
"address": "makassar"
});
```

### get data all future
```dart
await fs.getDataCollection("collection_name");
```

### get data all stream
```dart
StreamBuilder<QuerySnapshot<Map<String, dynamic>>>(
        stream: fs.getDataStreamCollection("collection_name"),
        builder: (context, snapshot) {
          final data = snapshot.data!.docs;
           ListView.builder(
              shrinkWrap: true,
              itemCount: data.length,
              itemBuilder: (BuildContext context, int index) {
              return Column(
                 children: [
                  ListTile(
                    title: Text(data[index]["name"])),
                  Divider(),
                ],
              );
```

### update data
```dart
await fs.updateDataAllDoc("collection_name", "id", {
"name": "shamil",
"address": "gowa"
});
```

### delete data
```dart
await fs.deleteDoc("collection_name", "id");
```

## Firebase Auth

### register with email and password
```dart
await fs.registerWithEmailAndPassword("email", "password");
```

### sign in with email and password
```dart
await fs.signInWithEmailAndPassword("email", "password");
```

### sign in with email and password
```dart
await fs.resetPassword("email");
```




