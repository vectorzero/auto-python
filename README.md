# 自动执行任务

1. [安装python3.4以上版本，并配置环境变量](https://www.runoob.com/python3/python3-install.html)

2. 安装依赖包

      ``` shell
      pip install pyperclip
      pip install xlrd
      pip install pyautogui
      pip install opencv-python
      pip install pillow
      ```

      `pyperclip` 模块有 copy() 和 paste() 函数， 可以向计算机的剪贴板发送文本，或从
      它接收文本。将程序的输出发送到剪贴板， 使它很容易粘贴到邮件、文字处理程序
      或其他软件中

      `xlrd`是python读取excel文件内容的库

      `pyautogui`模块可以通过屏幕xy坐标系统确定目标位置，控制鼠标和键盘发送虚拟击键和鼠标点击，完成点击按钮、填写表单等操作

      `opencv`是一个强大的图像处理和计算机视觉库

      `pillow`是PIL的一个派生分支，但如今已经发展成为比PIL本身更具活力的图像处理库

3. 把每一步要操作的图标、区域截图保存至本文件夹  png格式（注意如果同屏有多个相同图标，回默认找到最左上的一个，因此怎么截图，截多大的区域，是个学问，如输入框只截中间空白部分肯定是不行的，宗旨就是“唯一”

4. 在cmd.xls 的sheet1 中，配置每一步的指令，如指令类型1234  对应的内容填截图文件名，指令5对应的内容是等待时长（单位秒） 指令6对应的内容是滚轮滚动的距离，正数表示向上滚，负数表示向下滚

5. 双击auto.py打开程序，按1表示excel中的指令执行一次，按2表示无限重复执行直到程序关闭

6. 如果报错不能运行用vscode运行看看报错内容

7. 开始程序后请将程序框最小化，不然程序框挡住的区域是无法识别和操作的

8. 如果程序开始后因为你选择了无限重复而鼠标被占用停不下来，alt+F4吧~

9. 打包前准备

    - 下载安装[Anaconda](https://www.anaconda.com/products/individual)

    - 下载[opencv_python.whl](lfd.uci.edu/~gohlke/pythonlibs/)

    选择`opencv_python‑4.5.4‑cp37‑cp37m‑win_amd64.whl`，其中cp37代表python的版本

    将该文件放在*C:\ProgramData\Anaconda3\Scripts*路径下，其中*C:\ProgramData\Anaconda3*是Anaconda3的安装路径

10. 打包
      在项目目录下执行

      ```shell
      pip install pyinstaller
      pyinstaller -F -i auto.ico auto.py
      ```

11. 参考文章

      [xxx is not a supported wheel on this platform](https://blog.csdn.net/happywlg123/article/details/107281936)
