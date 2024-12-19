安装环境
确认您的开发环境安装了如下软件

# 1. 安装Python3

brew search python

# 选择安装的版本python@3.9、python@3.10等

brew install python3@x

# 2. 安装依赖包

pip install lxml beautifulsoup4 html5lib prompt_toolkit

# 安装依赖包解决方案
# 创建虚拟环境
python3 -m venv myenv

# 激活虚拟环境
source myenv/bin/activate

# 安装包
pip install lxml beautifulsoup4 html5lib prompt_toolkit

# 3. 安装lzo

brew install lzo

# 5. 安装Python lzo依赖包

pip install python-lzo

# 6. 下载Dictionary Development Kit

git clone https://github.com/SebastianSzturo/Dictionary-Development-Kit

# 7. 下载转换工具pyglossary

git clone https://github.com/ilius/pyglossary
转换.mdx字典


## 转换
python3 main.py --write-format=AppleDict Dictionary.mdx $directory-name/generate.vocabulary

复制词典原来附随的css样式，粘贴到$directory-name下的css文件中.
在.plist文件第10行更改的CFBundleDisplayName值，这将会是是词库在词典显示的名字

# 问题

# 很多教程都是用这个命令来进行转换的，但是我遇到了问题：资源文件无法提取出来，只有文本文件

# python /Users/apple/Desktop/Study/Python/pyglossary/main.py --write-format=AppleDict "/Users/apple/Desktop/Study/Python/File/LDOCE6.mdx" "LDOCE6"

# 这个命令可提取文本和所有资源（音频文件、图片等）

python /Users/apple/Desktop/Study/Python/pyglossary/pyglossary.pyw -u cmd

> Input file: /Users/apple/Desktop/Study/Python/File/LDOCE6.mdx
> Output file: /Users/apple/Desktop/Study/Python/File/LDOCE6
> Output format: AppleDict
> 编译安装字典
> 1.
> 进入LDOCE6目录

2.
打开Makefile文件

3.
修改DICT_BUILD_TOOL_DIR的路径，填写Dictionary-Development-Kit的所在目录的绝对路径即可（相对路径没有测试）

`
DICT_BUILD_TOOL_DIR	=	"/Users/wscrlhs/doc/dictionary/tmp/Dictionary-Development-Kit"
`

4.
进入Dictionary-Development-Kit的目录，修改其bin目录下的build_dict.sh文件，详情见make过程中可能会出现的问题

5.
进入LDOCE6目录，在终端使用make进行编译
make && make install
