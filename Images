import 'package:flutter/material.dart';
import 'package:image_picker/image_picker.dart';
import 'dart:io';

void main() {
  runApp(CameraGalleryApp());
}

class CameraGalleryApp extends StatefulWidget {
  @override
  _CameraGalleryAppState createState() => _CameraGalleryAppState();
}

class _CameraGalleryAppState extends State<CameraGalleryApp> {
  File? _image;
  final ImagePicker _picker = ImagePicker();

  Future<void> _pickImage(ImageSource source) async {
    final XFile? pickedFile = await _picker.pickImage(source: source);
    if (pickedFile != null) {
      setState(() {
        _image = File(pickedFile.path);
      });
    }
  }

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: Text("Camera & Gallery")),
        body: Center(
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: [
              _image == null
                  ? Text("No image selected")
                  : Image.file(_image!, height: 300),
              SizedBox(height: 20),
              ElevatedButton(
                onPressed: () => _pickImage(ImageSource.camera),
                child: Text("Capture Image"),
              ),
              ElevatedButton(
                onPressed: () => _pickImage(ImageSource.gallery),
                child: Text("Select from Gallery"),
              ),
            ],
          ),
        ),
      ),
    );
  }
}
