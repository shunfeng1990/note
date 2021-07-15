# Python GUI - PyQt5

参考指南：https://www.riverbankcomputing.com/static/Docs/PyQt5/

#### 安装PyQt5

1. 安装命令

```sh
pip3 install PyQt5
sudo apt-get install qttools5-dev-tools
sudo apt-get install qt5-default
sudo apt install pyqt5-dev-tools
```

2. 配置Pycharm

#### 文件 - 设置 - 工具 - 外部工具 - 点击 + 号 - 开始编辑工具

#### 工具1. 配置QtDesigner - 用于Pycharm可以直接启动QtDesigner：

名称：QtDesigner  	组：Qt5

描述：Qt Designer

程序：/usr/bin/designer

参数：$FileName$

工作目录：$ProjectFileDir$

#### 工具2. 用于将ui文件转换成py文件

名称：PyUIC  	组：Qt5

描述：Py UI to pyfile

程序：/usr/bin/python3

参数：-m PyQt5.uic.pyuic  $FileName$ -o $FileNameWithoutExtension$.py

工作目录：$FileDir$

> 然后点击菜单上面的工具就发现会有Qt5了 里面就有对应的工具了



选择 QtDesigner 设计窗口，保存到项目目录后，点击右键 选择 Qt5里面的 PyUIC 转换成 py文件

添加入口代码，方可执行py文件 打开窗口

```python
import sys
# 程序入口,程序从此处启动 PyQt 设计的窗口
if __name__ == '__main__':
    app = QtWidgets.QApplication(sys.argv)
    MainWindow = QtWidgets.QMainWindow()  # 创建窗口
    ui = Ui_MainWindow()  # 创建PyQt 设计的窗口
    ui.setupUi(MainWindow)  # 初始化设置
    MainWindow.show()  # 显示窗口
    sys.exit(app.exec_())  # 程序关闭时退出进程
```

> py文件打包成exe文件 需要安装 pyinstaller

#### 如提示“PyInstaller：未找到命令” 则执行如下命令：

```sh
sudo cp /home/andy/.local/bin/pyinstaller /usr/bin/pyinstaller  # andy为用户名
```

