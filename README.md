
## 背景交代
相信每个程序员都有自己做过个人网站,博客之类的项目了，但是现在还在维护吗？反正我前前后后做过2到3个了，维护一段时间后因为一些不可逆的原因(主要是懒)都没有维护了，购买的一些域名和服务器信息也都过期了，最近玩了一下hexo，发现这个东西挺方便的，基本半个小时就可以搞完，并且如果 完全托管在github上基本就是0成本，用作学习记录输出是够了。

### 1.依赖于nodejs安装，安装nodejs和npm
下载地址，可以对照电脑系统版本进行下载安装：https://nodejs.org/en/download/
现在nodejs的安装包内置了npm，所以下载安装完成之后，nodejs和npm都会安装好

检查安装是否成功
<img src="http://liuthing.com/images/hexo01/1.png" /><br/>
安装成后会显示出对应的版本信息，由于我电脑之前就安装过了，所以应该不是最新的版本

### 2.安装hexo
安装命令：
``` bash
$ sudo npm i -g hexo
```
<img src="http://liuthing.com/images/hexo01/2.png" /><br/>
直接一步就安装完成了,然后可以通过hexo -v查看是否安装成，成功安装的话，会打印出上面截图中的一些版本信息

### 3.hexo初始化博客项目
命令：
``` bash
$ hexo init
```
<img src="http://liuthing.com/images/hexo01/3.png" /><br/>
初始化完成之后，看看hexo在文件夹给我生成了哪些文件
<img src="http://liuthing.com/images/hexo01/4.png" /><br/>
如果你是一名前端或者nodejs开发者，相信对这些文件再熟悉不过了，还是对上述几个文件简单解释一下：
node_modules：存放依赖包信息
public：存放生成的页面
scaffolds：存放生成文章的一些模板
source：存放用命令创建的各种文章
themes：存放博客使用的主题
_config.yml：存放整个博客的配置
db.json：存放source解析所得到的
package.json：存放项目所需模块项目的配置信息

### 4.将生成的博客项目跑起来
``` bash
1、清除
hexo clean
2、生成
hexo g
3、启动服务
hexo server
```
<img src="http://liuthing.com/images/hexo01/5.png" /><br/>
启动完成后就可以按照提示，打开  http://localhost:4000  来访问我们在本地初始化好的博客项目了
<img src="http://liuthing.com/images/hexo01/6.png" /><br/>
可以看到我们的项目已经成功跑起来了，成功的迈出了第一步，先暂且按耐住激动的心情，我们继续！

### 5.在GitHub上创建仓库用于托管博客项目
<img src="http://liuthing.com/images/hexo01/7.png" /><br/>
仓库名称需要配置为：个人名字.github.io，仓库设置为公开，然后点击创建就可以

### 6.配置_config.yml
``` bash
deploy:
   type: git
   repository: https://github.com/PeyShine/PeyShine.github.io.git
   branch: master
```

### 7.上传项目
在此之前请先安装一个插件
``` bash
npm install hexo-deployer-git --save
```

部署（上传到GitHub）
``` bash
hexo d 或者 hexo deploy
```
<img src="http://liuthing.com/images/hexo01/8.png" /><br/>
上传过程中输入了用户名和密码，如果提前配置好ssh也可以不用输入

到Github上看一下，是否上传成功
<img src="http://liuthing.com/images/hexo01/9.png" /><br/>

可以看到文件都已经上传成功了

### 8.成功访问
通过域名“peyshine.github.io” 来访问
<img src="http://liuthing.com/images/hexo01/10.png" /><br/>