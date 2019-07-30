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

