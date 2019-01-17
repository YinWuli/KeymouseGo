# KeymouseGo v1.2

功能：记录用户的鼠标键盘操作，通过触发按钮自动执行之前记录的操作，可设定执行的次数，可以理解为 `精简绿色版` 的 `按键精灵`。

用途：在进行某些操作简单、单调重复的工作时，使用本软件就可以很省力了。自己只要做一遍，然后接下来就让电脑来做。


----------------------

该软件通过 `Python` 语言编写，已编译为 `windows` 平台可执行文件，未安装 `Python` 的用户可直接下载 `release` 版本 https://github.com/taojy123/KeymouseGo/releases ，直接点击 `KeymouseGo.exe` 运行

<img src="https://raw.githubusercontent.com/taojy123/KeymouseGo/master/sample.png" width="365">

----------------------

# 基本操作：

1、点击 `录制` 按钮，开始录制。

2、在计算机上进行任意操作，如点击鼠标、键盘输入，这部分的操作会被记录下来。

3、点击 `结束` 按钮，结束录制。

4、点击 `启动` 按钮，计算机会重复执行一遍第2步中所录制的操作。


# 提示：

1、可设置脚本重复执行的次数，如果为 `0` 即为无限循环。

2、默认启动热键为 `F8`，功能等同于 `启动` 按钮；默认终止热键为 `F12`，按下后将会停止正在运行的脚本。

3、录制时只记录鼠标点击动作和键盘操作，不记录鼠标移动轨迹。

4、每次录制结束后都会在 `scripts` 目前下生成一个新的脚本文件。

5、运行前可以在列表中选择一个需要执行的脚本。

6、`scripts` 下的脚本文件内容可以修改，修改时可参考如下所述的 `脚本格式说明`。


# 脚本格式说明：

```
[
 ["EM", "mouse left down", [100, 200], 3000], 
 ["EM", "mouse left up", [100, 200], 50], 
 ["EK", "key down", [70, "F"], 1000], 
 ["EK", "key up", [70, "F"], 50], 
 ["EM", "mouse right down", [300, 400], 2000], 
 ["EM", "mouse right up", [300, 400], 50]
]
```


每一行代表一次操作：
+ 每行的第 1 个元素表示鼠标操作或是键盘操作：`EM` 为鼠标，`EK` 为键盘
+ 每行的第 2 个元素表示操作的类型：`mouse left down` 为鼠标左键按下，`mouse left up` 为鼠标左键抬起，`mouse right down` 为鼠标右键按下，`mouse right up` 为鼠标右键抬起，`key down` 键盘按键按下，`key up` 键盘按键抬起
+ 每行的第 3 个元素表示具体的操作参数，由两个子元素构成，鼠标操作时两个子元素为鼠标所在的屏幕位置的横纵坐标，键盘操作时第一个子元素为按键码，如例子中的 `F` 按键码为 `70`，以此类推 `G` 按键码就是 `71`，第二个子元素在脚本运行时没有作用，可看做是一个备注说明
+ 每行的第 4 个元素表示操作延时，指的是本次操作与上一次操作之间的间隔，单位为毫秒
+ 修改时请严格遵守格式，否则可能导致脚本无法运行，建议修改前先备份一下


综上所述，示例中的脚本运行后的效果为：
+ 开始运行 `3000ms` 后，在屏幕坐标 `(100,200)` 处 `按下鼠标左键`
+ 等待 `50ms` 后在相同位置 `抬起鼠标左键`
+ 等待 `1000ms` 后 `按下F键`
+ 等待 `50ms` 后 `抬起F键`
+ 等待 `2000ms` 后，在屏幕坐标 `(300,400)` 处 `按下鼠标左键`
+ 等待 `50ms` 后在相同位置 `抬起鼠标左键`


----------------------

# 更新说明

## v1.2
+ UI 更新
+ 移除了 `后台模式`
+ 简化了录制脚本，增强了可读性
+ 脚本文件名优化，可录制多个脚本，避免误操作覆盖了辛辛苦苦录制的脚本
+ 可自定义 `启动热键` 和 `终止热键`








