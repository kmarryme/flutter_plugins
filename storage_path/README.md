# StoragePath

一个flutter插件，以json格式获取所有图像，音频，视频和文件的位置路径。仅限Android

```dart
dependencies:
 storage_path: ^0.2.1
```


```dart
import 'package:storage_path/storage_path.dart';
```
样例代码
```dart 
 try {
      imagePath = await StoragePath.imagesPath; //包含json格式的图像路径和文件夹名称
      videoPath = await StoragePath.videoPath; //这将返回视频路径
      audioPath = await StoragePath.audioPath; //这将返回音频路径
      filePath = await StoragePath.filePath; //这将返回文件路径[pdf,doc,docx,xls,xlsx,ppt,pptx,txt,rtx,rtf,html,apk,zip,rar,xml]
    } on PlatformException {
      imagesPath = 'Failed to get path';
    }
```

图片Json示例
 ```json 

[
  {
    "files": [
      "path/screenshot/abc.png",
      "path/screenshot/pqr.png"
    ],
    "folderName": "screenshot"
  }
]
  ```
文件Json示例
```json
[
  {
    "files": [
      {
        "mimeType": "application/pdf",
        "size": "34113",
        "title": "C001-SP-2719^201902",
        "path": "/storage/emulated/0/Download/abc.pdf"
      }
    ],
    "folderName": "Download"
  }
]
```
音频Json示例
```json
[
  {
    "files": [
      {
        "album": "ABC",
        "artist": "PQR",
        "path": "/storage/emulated/0/Download/todo.mp3",
        "dateAdded": "1515060080",
        "displayName": "todo.mp3",
        "duration": "235986",
        "size": "9506989"
      }
    ],
    "folderName": "Download"
  }
]
```
视频Json示例
```json
[
  {
    "files": [
      {
        "path": "/storage/emulated/0/DCIM/Camera/VID_20190304_112455.mp4",
        "dateAdded": "1551678904",
        "displayName": "VID_20190304_112455.mp4",
        "duration": "7147",
        "size": "12787914"
      }
    ],
    "folderName": "Camera"
  }
]
```
