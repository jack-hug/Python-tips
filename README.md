# Python-tips
_建立一个仓库，放一些学习Python过程中遇到的问题及解决方法_



## first:解决pip下载速度过慢问题
很多扩展使用的都是国外链接，国外链接的下载速度实在太慢，所以在网上找了一些国内镜像，可以大幅度提升下载速度及安装效率。
*但是个人有一些疑问，不懂这些包的版本是不是随时跟着国外包的更新而更新，不过目前来看，这不是我主要担心的问题*

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

安装包： pip install virtrualenv

虚拟环境设置：
1.转到要安装虚拟环境的文件夹,如D:\\git\\flask (命令行执行)

2.执行命令 virtualenv --no-site-packages venv (--no-site-packages表示不复制Python环境中的所有第三方包，但其实可以不用这个参数，因为我试过，大多数情况下，虚拟环境都不会安装其他包，可能会有例外，但目前没发现)

3.激活虚拟环境
Linux:source venv/bin/activate
Windows: venv\Scripts\activate
Powshell: . venv\scripts\activate

4.退出虚拟环境
deactivate

5.虚拟环境迁移
当需要在不同的虚拟环境使用相同的包时，可以用pip freeze>requirments.txt命令。
举例：有虚拟环境venv1和venv2，venv2要装上venv1里面的所有包。
解决步骤：
(1).在venv1下运行命令行:pip freeze>requirments.txt，将所以的包导出到requirments.txt文件。
(2).把requirments.txt复制到venv2项目的根目录。
(3).在虚拟环境venv2下执行命令安装包：pip install -i https://mirrors.aliyun.com/pypi/simple/ -r requirements.txt 
这样就会把venv1里面所有的包都安装到venv2的虚拟环境里面

6.vscode里面使用虚拟环境
只要vscode发现你项目文件里面有venv文件夹，好像就会自动帮你在虚拟环境下调试项目，vscode的左下角也可以选择调试环境。

7.在powshell运行虚拟环境时会失败。此时是因为powshell禁止运行不信任脚本。以管理员身份运行powshell，输入Set-ExecutionPolicy RemoteSigned，然后选择“是”，这个问题就可以解决。但是用powshell激活虚拟环境时，与CMD对比，要在前面多添加一个点,如：. venv\scripts\activate

## third:vscode settings Sync 同步设置

之前因为一次误操作，在使用sync同步设置时，一直出现一个错误：Sync:inavlid gist id,重置了很多遍都没有效果。后来按如下操作，总算搞定了。

1.安装Sync，若已经安装，可用快捷键 Ctrl+Shift+P，输入 Sync,找到重置扩展设置（Reset Extension Settings）来使之初始化。

2.重启vscode，在Sync 首页点击 LOGIN WITH GITHUB 按钮，登录github；之后会跳出一个页面，如果是第一次登录或者误删了gists，可以点击skip,之后会自动帮你创建一个名为cloudSettings的gist，稍等十几秒，Sync自动帮你把目前的配置上传到github。

3.在其他电脑打开VSCODE，装好Sync扩展，同样步骤登录，此时可能会要求输入Token,输入之后就可以同步了。

注1：两个快捷键 Shift+Alt+U上传，Shift+Alt+D下载。

注2：当提示**Sync:invalid gist id**时，一定要检查一下设置里面的gist是否已经存在。点击左下角设置-输入：gist，在用户及工作区都检查一下gist,一定要保证是空。

