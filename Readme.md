
# 前言

&emsp;&emsp;好看的皮囊千篇一律，有趣的灵魂万里挑一。最近在学习`C#`，接触到了`winform`，记得曾经在抖音上看到过这样一个小程序，觉得很有意思，就用C#语言实现了下，实现起来很简单（可以说没有任何技术含量）程序执行后效果如下。

&emsp;&emsp;**视频演示**    [传送门](https://www.bilibili.com/video/BV1wK4y1m7Li)


![](https://img-blog.csdnimg.cn/img_convert/5b556b7291658cef750c4ebf25b420d2.gif#pic_center)

---
# 第一步：创建项目

## 1、创建windows窗体应用程序
![](https://img-blog.csdnimg.cn/img_convert/a48a4a92ec014cd68e5174229f6e8028.png#pic_center)
## 2、更改项目名称和储存位置
![](https://img-blog.csdnimg.cn/img_convert/97ae8b0250553baba20d190bb3b13097.png#pic_center)
## 3、选择合适的.NET框架
![](https://img-blog.csdnimg.cn/img_convert/0478e723fc6874648bcb28b67d7489c1.png#pic_center)
## 4、项目创建完成
![](https://img-blog.csdnimg.cn/img_convert/11a3f9c3af83ba3494315ec9132f2c39.png#pic_center)

---
# 第二步：设计窗体
&emsp;&emsp;通过左侧工具箱拖拽绘制窗口，`Label`显示文本，`pictureBox`显示图片，`Button`按钮等，各控件可在右侧修改属性，包括标题栏内容，程序图标，文本的字体大小内容，图片大小内容，按钮的文字等。

## 1、添加控件
![](https://img-blog.csdnimg.cn/img_convert/61d6d6f473bcf1f2ace037d7ec1dcfd1.png#pic_center)
## 2、更改属性
![](https://img-blog.csdnimg.cn/img_convert/dd32bb35008aaebcf3fa5085ea4a9f96.png#pic_center)
&emsp;&emsp;**图片加载方法**

![](https://img-blog.csdnimg.cn/img_convert/9d783aee10f00b5dcda9b99b8e18c357.png#pic_center)
## 3、更改窗体属性
![](https://img-blog.csdnimg.cn/img_convert/3f9ad6a63c051ac564991e1a2ceea334.png#pic_center)

---
# 第三步：添加事件

## 1、添加[好呀]事件

&emsp;&emsp;双击[好呀]按钮，进入点击事件代码编辑区，添加如下代码。

```csharp
            MessageBox.Show("我就知道你会同意的", "^v^");
            MessageBox.Show("恭喜你拥有一名可爱的男朋友~~", "^v^");
            MessageBox.Show("🤍🤍爱你，么么哒🤍🤍", "^v^");
            this.Dispose();
```
![](https://img-blog.csdnimg.cn/img_convert/0cd8ed6bc32d9c1193f5c2d04b231d63.png#pic_center)
## 2、添加[算了吧]事件

&emsp;&emsp;选中`[算了吧]`按钮，点击右侧属性栏中的`事件`图标，在下面找到`MouseEnter`事件，双击`MouseEnter`事件添加如下代码。

```csharp
            int x = this.ClientSize.Width - button2.Width;
            int y = this.ClientSize.Height - button2.Height;
            Random r = new Random();
            button2.Location = new Point(r.Next(0, x + 1), r.Next(0, y + 1));
```

![](https://img-blog.csdnimg.cn/img_convert/d4340652232cc3f6f29b9d172762e48d.png#pic_center)
![](https://img-blog.csdnimg.cn/img_convert/decae46c893ba9f6df9ffc242b297487.png#pic_center)
## 3、禁用关闭窗口

&emsp;&emsp;选中`form1`窗体，点击右侧属性栏上面的`事件`图标，在下面找到`FormClosing`事件，然后双击`FormClosing`事件添加如下代码。

```csharp
            MessageBox.Show("不回答不能退出哦！", "(╯_╰)╭");
            e.Cancel = true;
```
![](https://img-blog.csdnimg.cn/img_convert/ed4234223be9c924ec67ab5ebdeef9a8.png#pic_center)
![](https://img-blog.csdnimg.cn/img_convert/7c4831bc619e449aeecd51ebc4ba364e.png#pic_center)

---
# 第四步：调试生成打包程序

## 1、调试（F5/CTRL+F5）

&emsp;&emsp;调试程序发现`算了吧`按钮在移动时会被其他控件遮挡（这和你一开始拖控件的顺序有关，如果出现这种情况，我们可以右键将控件置于顶层）

![](https://img-blog.csdnimg.cn/img_convert/0d21fd084937aba1d4777350e60cc3a4.png#pic_center)
![](https://img-blog.csdnimg.cn/img_convert/91d06b882e0ba9b0ec7953c621f29086.png#pic_center)
## 2、更改应用程序（生成的.exe）图标
&emsp;&emsp;右键项目解决方案，更改图标，图标格式应为`.ico`格式

![](https://img-blog.csdnimg.cn/img_convert/b3257cfd1baa58ca0a8741e95a68e32b.png#pic_center)
## 3、生成

&emsp;&emsp;选择`release`生成发布版本，`debug`版本内容包含调试代码，`release`版本是代码优化后的发布版本。

![](https://img-blog.csdnimg.cn/img_convert/6fb29ba6f7248d3465623028dddbddb3.png#pic_center)
&emsp;&emsp;右键项目解决方案，生成程序！

![](https://img-blog.csdnimg.cn/img_convert/c5faef2a498cd7542ec62f7a98c383e8.png#pic_center)
## 4、打包

&emsp;&emsp;生成之后，在你项目储存的位置的相应目录下会出现如下内容，我们可以双击运行`Love.exe`这就是最终成果。

![](https://img-blog.csdnimg.cn/img_convert/90fcc33b8257a1c2f3f10df6cd6023f6.png#pic_center)

&emsp;&emsp;倘若将此程序发送给小伙伴，在小伙伴电脑上运行成功，则需要拷贝或打包此目录下的所有文件，并且如果小伙伴的电脑上没有`.NET5.0`框架的话，运行此程序时，系统会提示安装框架。
&emsp;&emsp;当然如果你一开始就使用的是低版本的`.NET`框架，发送给小伙伴时，小伙伴便不需要安装低版本框架。


