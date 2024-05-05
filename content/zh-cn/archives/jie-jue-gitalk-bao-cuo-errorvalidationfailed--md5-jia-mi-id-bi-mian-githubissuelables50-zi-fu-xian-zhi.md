---
title: 解决：gitalk 报错 Error: Validation Failed.--MD5 加密 id 避免 github issue lables 50 字符限制
id: 480
date: 2023-10-17 08:43:40
auther: admin
excerpt: 创建一个github gist 文件保存https//github.com/blueimp/JavaScript-MD5/blob/master/js/md5.min.jsjs 源码：https//gist.githubusercontent.com/qhh0205/78e9e0b1f3114d
permalink: /archives/jie-jue-gitalk-bao-cuo-errorvalidationfailed--md5-jia-mi-id-bi-mian-githubissuelables50-zi-fu-xian-zhi
categories:
 - share
tags: 
 - gitalk
---

 创建一个github gist 文件保存
https://github.com/blueimp/JavaScript-MD5/blob/master/js/md5.min.js 
js 源码：
https://gist.githubusercontent.com/qhh0205/78e9e0b1f3114db6737f3ed8cdd51d3a/raw/3894c5be5aa2378336b1f5ee0f296fa0b22d06e9/md5.min.js
将 gist 链接嵌入到 layout/_third-party/comments/gitalk.swig 文件，嵌入时的 js 链接地址需要注意下：

不能直接写第一步的创建的 gitst 链接地址，需要将 gist.githubusercontent.com 替换为 rawgit.com。即嵌入地址为: https://rawgit.com/qhh0205/78e9e0b1f3114db6737f3ed8cdd51d3a/raw/3894c5be5aa2378336b1f5ee0f296fa0b22d06e9/md5.min.js

最终 layout/_third-party/comments/gitalk.swig 配置如下：
```JS
{% if page.comments && theme.gitalk.enable %}
  <link rel="stylesheet" href="https://unpkg.com/gitalk/dist/gitalk.css">
  <script src="https://unpkg.com/gitalk/dist/gitalk.min.js"></script>
  <script src="https://rawgit.com/qhh0205/78e9e0b1f3114db6737f3ed8cdd51d3a/raw/3894c5be5aa2378336b1f5ee0f296fa0b22d06e9/md5.min.js"></script>
   <script type="text/javascript">
        var gitalk = new Gitalk({
          clientID: '3840ba8c8d80c18be7e3',
          clientSecret: '1b00f2efe5285973c24da9ed9ac895775eacc8ea',
          repo: '{{ theme.gitalk.repo }}',
          owner: '{{ theme.gitalk.githubID }}',
          admin: ['{{ theme.gitalk.adminUser }}'],
          id: md5(location.pathname),
          distractionFreeMode: '{{ theme.gitalk.distractionFreeMode }}'
        })
        gitalk.render('gitalk-container')
    </script>
{% endif %}
```