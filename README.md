ExUI, Inspired by WeUI, Antui, Ionic, Sui and Bootstrap.
====

## 概述

ExUI 是一套借鉴多套UI库衍生出来的重复车轮，整体结构抄袭了微信的 WeUI, 部分参考了阿里的 Antui、Sui，还有Ionic、Bootstrap，同时借鉴了Semantic-UI对于class的命名习惯。
从整体来说，ExUI其实就是借鉴成熟流行的框架，加上一些(好的)个人喜好的集成。

## 命名
命名我参照了Semantic-UI的命名习惯，因为我不喜欢prefix的命名习惯，觉得像老太太的裹脚布。
当然这也可能导致与现存项目命名冲突，所以ExUI更适合作为新项目的基础UI模板，而并不适合作为插件迁移到已有的项目中，这可能导致各种样式命名冲突，当然你也可以自行修改源码编译以便适应你的项目。

## 1PX
由于DPR的不同，之前的项目里采用了阿里的Flexible方案，但是这衍生出多个问题：
1. 构建复杂度上升，需要将现有的CSS单位由PX转换成REM，无法使用Css sprite，无法使用内联style，在HTML页面内嵌style元素都需要经过PX TO REM的转换。
2. 各种莫名其妙的小问题：比如INPUT经过缩放，在PC开发模拟和某些Andriod机型时，经常无法通过点击聚焦。
3. 当需要输入第三方富文本的时候无法直接输出：比如你在构建商城，商品详情是后台录入的编辑器输出的，由于框架采用了缩放方案会导致同时也会缩放富文本，这就出现缩小问题，为了解决你依然需要在输出时进行转换，但是又由于富文本编辑器有时候你无法预知单位，这会照成很多麻烦，比如它会使用PT而不是PX。
4. 由于很多Android设备不支持延迟生成viewport，为了完美匹配手机型号，引入了比较繁杂的脚本来识别UA的设备类型。

**所以最终放弃了Flexible的方案** 1PX的显示方案采用了WeUI的scale方法。

## 手机预览

扫码体验：

![https://weui.io](https://cloud.githubusercontent.com/assets/4652816/15662614/178efd46-2725-11e6-8952-09d7836e968d.png)

链接预览：
[https://weui.io](https://weui.io)

## 字体

内置的ICON使用的是阿里妈妈的开源字体库，你可以通过这个链接查看到内置的字体内容:
http://at.alicdn.com/t/font_u6f8kl0ov9y919k9.css
你也可以通过http://www.iconfont.cn/ 来构建适合自己的字体库来替换项目内置的，当然需要重新build整个工程，并修改部分示例中的icon编码。

## License
The MIT License(http://opensource.org/licenses/MIT)

请自由地享受和参与开源

## 贡献

如果你有好的意见或建议，欢迎给我提issue或pull request.