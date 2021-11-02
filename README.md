# weapp-code
本项目是小程序兼容h5二维码的插件
使用方法如下：
## weapp
```js
var QR = require("./qrcode.js");
//调用插件中的draw方法，绘制二维码图片
QR.api.draw(url, canvasId, cavW, cavH, this);
```
## taro
```js
const QR = require('./qrcode.js');
await QR.api.draw(url, 'myQrcode', 200, 200, this, null, async () => {
  const res = await canvasToTempFilePath({
    x: 0,
    y: 0,
    width: dpr * 200,
    height: dpr * 200,
    destWidth: dpr * 200 * 6,
    destHeight: dpr * 200 * 6,
    canvasId: 'myQrcode',
    fileType: 'jpg',
    quality: 1,
  });
});
```

## api
|  参数   | 说明  | 类型 |
|  ----  | ----  | ---- |
| 第一个 | h5链接  | string |
| 第二个 | canvasId  | string |
| 第三个 | 获取canvas宽  | number |
| 第四个 | 获取canvas高  | number |
| 第五个 | 当前方法节点  | this |
| 第六个 | 等级  | number |
| 第七个 | 回调函数  | function |