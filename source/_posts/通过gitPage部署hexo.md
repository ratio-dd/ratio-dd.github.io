---
title: 通过GitPage部署hexo
date: 2022-07-12 21:51:21
tags: hexo
categories:
- hexo
---

通过gitpage将hexo生成的静态网站部署。



## GitPage

GitHub Pages官网：https://pages.github.com/

gitpage整体的使用体验还是很简单的，通过github仓库去实现网站的部署。

与hexo的deploy功能可以很好的结合，hexo本身就对git有着很好的支持，通过

```shell
npm i hexo-deployer-git
```

安装相关插件后，在其默认的config中进行配置，如下图

![image-20220712221356591](https://s1.vika.cn/space/2022/07/12/7e50712eb3c749e7a7670fde011927b0)

然后运行`hexo deploy`即可自动配置。

注意此插件在hexo根目录生成了一个`.deploy_git`目录，进入后是一个与`public`目录同步的git仓库，如果需要增加图片等，在外部的`public`目录添加即可，此目录中内容尽量不要修改。

> 注意config中branch的设置，默认设置为master，如果本地分支映射错误会很麻烦，不是很好解决此问题。

gitpage中注意在仓库相关选项可以选择依照某一分支进行page生成，所以可以将gitpage和hexo源代码共同存储在同一仓库的**不同分支**上，不会造成影响，且可以达到多平台同步的效果。
