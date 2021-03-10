# Flutter  构建漂亮的原生应用

------

Flutter是谷歌的移动UI框架，可以快速在iOS和Android上构建高质量的原生用户界面。 Flutter可以与现有的代码一起工作。在全世界，Flutter正在被越来越多的开发者和组织使用，并且Flutter是完全免费、开源的。

> * 快速开发
>毫秒级的热重载，修改后，您的应用界面会立即更新。使用丰富的、完全可定制的widget在几分钟内构建原生界面
> * 富有表现力和灵活的UI
> 快速发布聚焦于原生体验的功能。分层的架构允许您完全自定义，从而实现难以置信的快速渲染和富有表现力、灵活的设计。

> * 原生性能
> Flutter包含了许多核心的widget，如滚动、导航、图标和字体等，这 些都可以在iOS和Android上达到原生应用一样的性能


![flutter-markdown-logo](https://www.4x-treme.com/wp-content/uploads/2020/03/fluttericon.png)



## 快速开发

**[Flutter](https://flutter.dev/)**的热重载可帮助您快速地进行测试、构建UI、添加功能并更快地修复错误。在iOS和Android模拟器或真机上可以在亚秒内重载，并且不会丢失状态。

### Flutter的特点

- [x] 富有表现力，漂亮的用户界面
- [x] 现代的，响应式框架
- [x] 访问本地功能和SDK
- [x] 统一的应用开发体验

### 富有表现力，漂亮的用户界面
> 使用Flutter内置美丽的MaterialDesign和Cupertino（iOS风格）widget、丰富的motion API、平滑而自然的滑动效果和平台感知，为您的用户带来全新体验。

### 现代的，响应式框架
> 使用Flutter的现代、响应式框架，和一系列基础widget，轻松构建您的用户界面。使用功能强大且灵活的API（针对2D、动画、手势、效果等）解决艰难的UI挑战。

### 访问本地功能和SDK
> 通过平台相关的API、第三方SDK和原生代码让您的应用变得强大易用。 Flutter允许您复用现有的Java、Swift或ObjC代码，访问iOS和Android上的原生系统功能和系统SDK。
访问平台功能非常简单。以下是interop example（互操作示例）中的一个片段：
```swift
Future<Null> getBatteryLevel() async {
  var batteryLevel = 'unknown';
  try {
    int result = await methodChannel.invokeMethod('getBatteryLevel');
    batteryLevel = 'Battery level: $result%';
  } on PlatformException {
    batteryLevel = 'Failed to get battery level.';
  }
  setState(() {
    _batteryLevel = batteryLevel;
  });
}
```

1813003 李昱龙

### end