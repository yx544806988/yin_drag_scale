# yin_drag_sacle

Image zooming in, zooming out, dragging, you can customize the zoom scale, the project is from flutter_drag_scale, the modification is published to meet their own project

图片缩放，缩放，拖动，可以自定义缩放比例，该项目是来自flutter_drag_scale，修改后发布，以满足自己的项目

## Getting Started

- amplification
    - gesture magnification
    - double click to enlarge
- to reduce the
- drag

- 放大
    - 手势放大
    - 双击放大
- 缩小
- 拖动


它可以配合轮播使用


```
import 'package:flutter/material.dart';
import 'package:flutter_swiper/flutter_swiper.dart';
import 'package:yin_drag_sacle/yin_drag_sacle.dart';

void main() => runApp(MyApp());

class MyApp extends StatefulWidget {
  @override
  MyAppState createState() => new MyAppState();
}

class MyAppState extends State<MyApp> {
  List<String> path = [
    'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1575024212241&di=b017d085f3982d951b9a365fbc9cfdd4&imgtype=0&src=http%3A%2F%2Fimg2.mukewang.com%2F5c18cf540001ac8206000338.jpg',
    'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1575024212240&di=a69285fddbc441702f83a707a2d2af17&imgtype=0&src=http%3A%2F%2Fdingyue.nosdn.127.net%2FetqmQabSGrqHXhTvzaS91gV006NWCPDnEgLHRoAVony8E1543979039684.png',
    'http://h.hiphotos.baidu.com/zhidao/wh%3D450%2C600/sign=0d023672312ac65c67506e77cec29e27/9f2f070828381f30dea167bbad014c086e06f06c.jpg',
  ];

  ///item 视图
  Widget itemView(BuildContext context, int index) {
    String value = path[index];
    return DragScaleContainer(
      child: Image(image: NetworkImage(value)),
      doubleTapStillScale: false,
      maxScale: 4, //放大最大倍数
    );
  }

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: Text('图片显示')),
        body: Swiper(
          itemBuilder: itemView,
          itemCount: path.length,
          pagination: SwiperPagination(),
          control: SwiperControl(),
        ),
      ),
    );
  }
}

```