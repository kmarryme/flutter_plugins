# screen_utils

一个用于调整屏幕和字体大小的flutter插件。让您的UI在不同的屏幕大小上显示合理的布局！

使用方法：

##### 1.在项目根目录pubspec.yaml引入

```dart
dependencies:
 screen_utils: 
    git:
      url: https://github.com/kmarryme/flutter_plugins.git
      path: screen_utils
```

##### 2. 在代码中引用

```dart
import 'package:screen_utils/screen_utils.dart';
```

##### 3. 在您的MaterialApp的第一个页面初始化

```dart
import 'package:flutter/material.dart';
import 'package:screen_utils/screen_utils.dart';

void main() async {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
        visualDensity: VisualDensity.adaptivePlatformDensity,
      ),
      home: Index(),
    );
  }
}

class Index extends StatelessWidget {
  const Index({Key key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    // 在第一个页面初始化插件
    // 默认值：宽度：375px，高度：812px，allowFontScaling：false
    Screen.init(context);
    //Screen.init(context, width: 750, height: 1334);
    //Screen.init(context, width: 750, height: 1334, allowFontScaling: true);
    
    return Scaffold(
      appBar: AppBar(),
    );
  }
}
```

##### 4.使用方法

    适应屏幕尺寸：
    传递设计图稿的px大小：
    适于屏幕宽度：Screen().width(540)
    适应于屏幕高度：Screen().height(200)，

```dart
///长方形
Container(
    width: Screen().width(375),
    height: Screen().height(200),
    ...
),

///正方形
Container(
    width: Screen().width(200),
    height: Screen().width(200),
    ...
),

///适配字体
Text(
    "适配字体",
    style: TextStyle(
        fontSize: Screen().sp(16),
    ),
),
Text(
    "适配字体",
    style: TextStyle(
        fontSize: Screen().sp(16, , allowFontScalingSelf: true),
    ),
),

///其他API
Screen.pixelRatio       //设备的像素密度
Screen.screenWidthDp    //当前设备宽度 dp
Screen.screenHeightDp   //当前设备高度 dp
Screen.screenWidth      //当前设备宽度 px
Screen.screenHeight     //当前设备高度 px
Screen.statusBarHeight  //状态栏高度 dp 刘海屏会更高
Screen.bottomBarHeight  //底部安全区距离 dp
Screen.scaleWidth       //实际宽度dp与UI设计px的比例
Screen.scaleHeight      //实际高度dp与UI设计px的比例
```


