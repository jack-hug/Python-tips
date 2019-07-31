# Python-tips
_建立一个仓库，放一些学习Python过程中经常遇到的问题及Tips_



## first:解决pip下载速度过慢问题
国外的资源的下载速度实在太慢，所以找到了一些国内镜像，可以大幅度提升下载速度及安装效率

国内源：
清华：https://pypi.tuna.tsinghua.edu.cn/simple

阿里云：https://mirrors.aliyun.com/pypi/simple/

中国科技大学 https://pypi.mirrors.ustc.edu.cn/simple/

华中理工大学：https://pypi.hustunique.com/

山东理工大学：https://pypi.sdutlinux.org/ 

豆瓣：https://pypi.douban.com/simple/

使用pip下载时加参数

例子：pip install -i https://mirrors.aliyun.com/pypi/simple/ flask

## second:虚拟环境 virtualenv

安装： pip install virtrualenv

1.转到要安装虚拟环境的文件夹,如D:\\git\\flask (命令行执行)

2.执行命令 virtualenv --no-site-packages venv (--no-site-packages表示不复制Python环境中的所有第三方包)

3.激活虚拟环境
Linux:source venv/bin/activate
Windows: venv\Scripts\activate

4.退出虚拟环境
deactivate

## third:vscode settings Sync 同步设置

之前因为一次误操作，在使用sync同步设置时候，一直出现一个错误：Sync:inavlid gist id,重置了很多遍都没有效果。后来按如下操作，总算搞定了。

1.安装Sync，若已经安装，可用快捷键 Ctrl+Shift+P，输入 Sync,找到重置扩展设置（Reset Extension Settings）来使之初始化。

2.在Sync 首页点击 LOGIN WITH GITHUB 按钮，登录github；之后会跳出一个页面，如果是第一次登录或者误删了gists，可以点击skip,之后会自动帮你创建一个名为cloudSettings的gist，稍等十几秒，Sync自动帮你把目前的配置上传到github。

3.在其他电脑打开VSCODE，装好Sync扩展，同样步骤登录，此时可能会要求输入Token,输入之后就可以同步了。

注1：两个快捷键 Shift+Alt+U上传，Shift+Alt+D下载。

注2：当提示**Sync:invalid gist id**时，一定要检查一下设置里面的gist是否已经存在。点击左下角设置-输入gist，在用户及工作区都检查一下gist,一定要保证是空。


