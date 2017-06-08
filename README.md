# Kubernetes Handbook

[Kubernetes](http://kubernetes.io)是Google基于[Borg](https://research.google.com/pubs/pub43438.html)开源的容器编排调度引擎，作为[CNCF](http://cncf.io)（Cloud Native Computing Foundation）最重要的组件之一，它的目标不仅仅是一个编排系统，而是提供一个规范，可以让你来描述集群的架构，定义服务的最终状态，它将自动的将系统达到和维持在这个状态。

本书记录了本人从零开始学习和使用Kubernetes的心路历程，着重于经验分享和总结，同时也会有相关的概念解析，希望能够帮助大家少踩坑，少走弯路。

在写作本书时，安装的所有组件、所用示例和操作等皆基于**Kubernetes1.6.0**版本。

[文章目录](SUMMARY.md)

GitHub地址：[https://github.com/rootsongjc/kubernetes-handbook](https://github.com/rootsongjc/kubernetes-handbook)

Gitbook在线浏览：[https://www.gitbook.com/book/rootsongjc/kubernetes-handbook/](https://www.gitbook.com/book/rootsongjc/kubernetes-handbook/)

## 如何使用本书

**在线浏览**

访问[gitbook](https://www.gitbook.com/book/rootsongjc/kubernetes-handbook/)

文中涉及的配置文件和代码链接在gitbook中会无法打开，请下载github源码后，在MarkDown编辑器中打开，点击链接将跳转到你的本地目录，推荐使用[typora](www.typorai.o)。

**本地查看**

1. 将代码克隆到本地
2. 安装gitbook：[Setup and Installation of GitBook](https://github.com/GitbookIO/gitbook/blob/master/docs/setup.md)
3. 执行gitbook serve
4. 在浏览器中访问[http://localhost:4000](http://localhost:4000)
5. 生成的文档在`_book`目录下

**生成pdf**

[下载Calibre](http://calibre-ebook.com/download)

* **On Mac**

在Mac下安装后，使用该命令创建链接

```
ln -s /Applications/calibre.app/Contents/MacOS/ebook-convert /usr/local/bin
```

在该项目目录下执行以下命令生成`kubernetes-handbook.pdf`文档。

```
gitbook pdf . ./kubernetes-handbook.pdf
```

* **On Windows**

需要用到的工具：[calibre](http://calibre-ebook.com/)，[phantomjs](http://phantomjs.org/download.html)

1. 将上述2个安装，calibre默认安装的路径`C:\Program Files\Calibre2`为你解压路径；
2. 并将其目录均加入到系统变量path中,参考:目录添加到系统变量path中；
3. 在cmd打开你需要转pdf的文件夹,输入`gitbook pdf`即可；

**生成单个章节的pdf**

使用`pandoc`和`latex`来生成pdf格式文档。

```shell
pandoc --latex-engine=xelatex --template=pm-template input.md -o output.pdf
```

## 如何贡献

### 提issue

如果你发现文档中的错误，或者有好的建议，不要犹豫，欢迎[提交issue](https://github.com/rootsongjc/kubernetes-handbook/issues/new)。

### 发起Pull Request

当你发现文章中明确的错误或者逻辑问题，在你自己的fork的分支中，创建一个新的branch，修改错误，push到你的branch，然后在[提交issue](https://github.com/rootsongjc/kubernetes-handbook/issues/new)后直接发起Pull Request。

### 贡献文档

#### 文档的组织规则

* 如果要创建一个大的主题就在最顶层创建一个目录；
* 全书五大主题，每个主题一个目录，其下不再设二级目录；
* 所有的图片都放在最顶层的`images`目录下，原则上文章中用到的图片都保存在本地；
* 所有的文档的文件名使用英文命名，可以包含数字和中划线；
* `etc`、`manifests`目录专门用来保存配置文件和文档中用到的其他相关文件；

#### 添加文档

1. 在该文章相关主题的目录下创建文档；
2. 在`SUMMARY.md`中在相应的章节下添加文章链接；
3. 执行`gitbook server`测试是否报错，访问 [http://localhost:4000](http://localhost:4000) 查看该文档是否出现在相应主题的目录下；
4. 提交PR

## 关于

[Jimmy Song](http://rootsongjc.github.io/about)

