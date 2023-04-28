# Flutter Progressive Image

A flutter widget which progressively loads large images using Low Quality Image Placeholders.

## Features

1. Displays placeholder and thumbnail image until the target Image loads.

2. Smooth Fade-in animations for preventing immediate image popups on load.

3. Blur effect for low resolution thumbnail to prevent the pixelated view.

4. Effectively resolves thumbnail image before the target image starts to fetch for quick first impression.

5. Placeholder widgets instead of placeholder images can now be added in v2.0.0

## Installing

Following steps will help you add this library as a dependency in your flutter project.

1. In the pubspec.yaml file in the root of your project

   ```
   dependencies:
   progressive_image: ^2.0.0
   ```
   
2. Run the following command to get packages:

   ```
   $ flutter packages get
   ```
   
3. Import the package in your project file:

   ```
   import 'package:progressive_image/progressive_image.dart';
   ```
   
## Usage

For a more detailed look at how to use this library, there is a sweet project in the example directory and various examples can be found here

A simple example usage of the ProgressiveImage widget is shown below:

   ```
   import 'package:flutter/material.dart';
import 'package:progressive_image/progressive_image.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  // This widget is the root of your application.
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: Text('Progressive Image Example')),
        body: ProgressiveImageExample(),
      ),
    );
  }
}

class ProgressiveImageExample extends StatelessWidget {
    @override
    Widget build(BuildContext context) {
        return Container(
            child: ProgressiveImage(
                placeholder: AssetImage('assets/placeholder.jpg'),
                // size: 1.87KB
                thumbnail: NetworkImage('https://i.imgur.com/7XL923M.jpg'),
                // size: 1.29MB
                image: NetworkImage('https://i.imgur.com/xVS07vQ.jpg'),
                height: 300,
                width: 500,
            ),
        );
    }
}
   ```