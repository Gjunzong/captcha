## 简介
captcha是一个图片验证码生成工具库,通过调用ImageCaptchaUtil中的方法来生成验证码图片信息,支持返回图片流,图片base64和图片base64Data。可设置干扰线类型来生成不同干扰类型的验证码图片。
## 自定义实现干扰类型
可通过继承AbstractDrawing类或实现IDrawing进行实现。继承AbstractDrawing只需要实现其中的绘制干扰线方法。实现IDrawing则需要手动实现所有的相关内容。
## 生成图片样例
![Image](https://github.com/niuchangqing/captcha/blob/master/src/test/java/org/ncq/captcha/image/example1.png)  
![Image](https://github.com/niuchangqing/captcha/blob/master/src/test/java/org/ncq/captcha/image/example2.png)  
![Image](https://github.com/niuchangqing/captcha/blob/master/src/test/java/org/ncq/captcha/image/example3.gif)  
![Image](https://github.com/niuchangqing/captcha/blob/master/src/test/java/org/ncq/captcha/image/example4.gif)  
![Image](https://github.com/niuchangqing/captcha/blob/master/src/test/java/org/ncq/captcha/image/example5.png)  
![Image](https://github.com/niuchangqing/captcha/blob/master/src/test/java/org/ncq/captcha/image/example6.gif)  
## 使用例子
```java
//静态图片,支持返回图片的base64,base64Data,byte[]
String code = RandomUtil.randomString(5);
String imageBase64Data = ImageCaptchaUtil.getImageBase64Data(code);
//指定图片宽度,高度
String imageBase64Data1 = ImageCaptchaUtil.getImageBase64Data(code,100,35);
//指定图片宽度,高度，干扰线数量
String imageBase64Data2 = ImageCaptchaUtil.getImageBase64Data(code,100,35,10);
//指定图片宽度,高度,干扰线数量,干扰线类型
String imageBase64Data3 = ImageCaptchaUtil.getImageBase64Data(code,100,35,10,InterferenceTypeEnum.LINE);
//其他更多参数,如字体，字体颜色,背景颜色，干扰线颜色等等详细参数请看ImageCaptchaUtil类中的具体方法;
```

```java
//gif动态图片,支持返回图片的base64,base64Data,byte[]
String code = RandomUtil.randomString(5);
String gifImageBase64Data = ImageCaptchaUtil.getGifImageBase64Data(code);
//指定图片宽度,高度
String gifImageBase64Data1 = ImageCaptchaUtil.getGifImageBase64Data(code,100,35);
//指定图片宽度,高度,干扰线数量
String gifImageBase64Data1 = ImageCaptchaUtil.getGifImageBase64Data(code,100,35);
//指定图片宽度,高度,干扰线数量,干扰线类型
String gifImageBase64Data1 = ImageCaptchaUtil.getGifImageBase64Data(code,100,35,InterferenceTypeEnum.LINE);
//其他更多参数,如字体，字体颜色,背景颜色，干扰线颜色等等详细参数请看ImageCaptchaUtil类中的具体方法;
```

## 常用随机字符串随机数字和随机运算字符串
RandomUtil类中实现了常用随机字符串数字等相关方法,方便用户生成code字符串
