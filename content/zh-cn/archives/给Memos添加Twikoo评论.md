---
title: 给Memos添加Twikoo评论
id: 3ab33161-4e2f-49b6-9a1f-ee2462ed76cd
date: 2023-12-27 08:40:07
auther: admin
excerpt: 代码来自于@林木木 2023.10.23更新脚本以适用于memos v0.16.1 自定义脚本 // Memos v0.16.1 单条页面插入 Twikoo 评论var twikooENV = 'https//你的.com/'function addTwikooJS() {   var me
permalink: /archives/1703637638658
categories:
 - share
tags: 
 - memos
---


代码来自于@[林木木](https://immmmm.com/memos-with-twikoo/)

2023.10.23更新脚本以适用于memos v0.16.1

## 自定义脚本
```
// Memos v0.16.1 单条页面插入 Twikoo 评论
var twikooENV = 'https://你的.com/'
function addTwikooJS() { 
  var memosTwikoo = document.createElement("script");
  memosTwikoo.src = `https://cdn.staticfile.org/twikoo/1.6.22/twikoo.all.min.js`;
  var tws = document.getElementsByTagName("script")[0];
  tws.parentNode.insertBefore(memosTwikoo, tws);
};
function startTwikoo() {
  startTW = setInterval(function(){
    var nowHref = window.location.href;
    var twikooDom = document.querySelector('#twikoo') || '';
    if( nowHref.replace(/^.*\/(m)\/.*$/,'$1') == "m"){
      if(!twikooDom){
        addTwikooJS()
        setTimeout(function() {
          var memoTw = document.querySelector('.gap-2') || '';
          memoTw.insertAdjacentHTML('afterend', '<div id="mtcomment"></div>');
          twikoo.init({
            envId: twikooENV,
            el: '#mtcomment',
            path: nowHref.replace(/^.*=?(http.*\/m\/[0-9]+).*$/,'$1'),
            onCommentLoaded: function () {
              startTwikoo();
            }
          })
        }, 1500)
      }else{
        clearInterval(startTW)
      }
    }
  }, 2000)
}
startTwikoo();
```

2023.10.17更新脚本
## 自定义脚本
适用于0.16版本

```
//Memos v0.16 添加 Twikoo 评论 v2023.10.06
var twikooENV = ''  //你的 https://xxxx/
function addTwikooJS() { 
  var memosTwikoo = document.createElement("script");
  memosTwikoo.src = `https://cdn.staticfile.org/twikoo/1.6.22/twikoo.all.min.js`;
  var tws = document.getElementsByTagName("script")[0];
  tws.parentNode.insertBefore(memosTwikoo, tws);
};
function startTwikoo() {
  startTW = setInterval(function(){ //定时执行 1秒/次
    var nowHref = window.location.href;
    var twikooDom = document.querySelector('#twikoo') || '';
    if( nowHref.replace(/^.*\/(m)\/.*$/,'$1') == "m"){//单条页面
      if(!twikooDom){
        //console.log('评论未加载');
        addTwikooJS() //加载评论 js
        setTimeout(function() { //延迟 1秒 执行
          var memoTw = document.querySelector('.resource-wrapper') || '';
          memoTw.insertAdjacentHTML('afterend', '<div id="mtcomment"></div>');
          twikoo.init({
            envId: twikooENV,
            el: '#mtcomment',
            path: nowHref.replace(/^.*=?(http.*\/m\/[0-9]+).*$/,'$1'), //v2023.08.09 正则更新
            onCommentLoaded: function () {
              startTwikoo()
              //console.log('再次开启定时执行');
            }
          })
        }, 900)
      }else{
        //console.log('清除定时执行');
        clearInterval(startTW)
      }
    }
  }, 2000)
}
startTwikoo();
```

由于官方已经有评论图标所以CSS不再添加图标

2023.9.26 更新.memos升级0.15.1版本后以下无法使用


## 自定义脚本

```json
//添加 twikoo 评论 v2023.06.10
var twikooENV = 'https://twikoo.jiong.us/'
function addTwikooJS() { 
  var memosTwikoo = document.createElement("script");
  memosTwikoo.src = `https://cdn.staticfile.org/twikoo/1.6.16/twikoo.all.min.js`;
  var tws = document.getElementsByTagName("script")[0];
  tws.parentNode.insertBefore(memosTwikoo, tws);
};
function addComIcon(){
  var memoTwIcons = document.querySelectorAll('.time-text') || '';
  if(memoTwIcons){
    for(var i=0;i < memoTwIcons.length;i++){
      //if(memoTwIcon[i].hasChildNodes == false){
        memoTwIcons[i].insertAdjacentHTML('afterbegin', '<div class="twicon"><svg class="icon" viewBox="0 0 1024 1024" xmlns="http://www.w3.org/2000/svg" width="16" height="16"><path d="M896 138.667H128c-38.4 0-64 25.6-64 64v544c0 38.4 25.6 64 64 64h128v128c83.2 0 166.4-44.8 256-128h384c38.4 0 64-25.6 64-64v-544c0-38.4-25.6-64-64-64zm0 608H486.4l-19.2 19.2c-51.2 51.2-102.4 83.2-147.2 96v-115.2H128v-544h768v544z" fill="#8a8a8a"/><path d="M256 477.867a64 64 0 1 0 128 0 64 64 0 1 0-128 0zM448 477.867a64 64 0 1 0 128 0 64 64 0 1 0-128 0zM640 477.867a64 64 0 1 0 128 0 64 64 0 1 0-128 0z" fill="#8a8a8a"/></svg></div>');
      //}
    }
  }
};
function startTwikoo() {
  start = setInterval(function(){
    var twikooDom = document.getElementById('twikoo') || '';
    var memoTw = document.querySelector('.memo-wrapper') || '';
    var memoLoading = document.querySelector('.action-button-container') || '';
    var memoLoadingA = document.querySelector('.action-button-container a') || '';
    var memoTwIcons = document.querySelectorAll('.time-text .twicon') || '';
    var nowHref = window.location.href;
    if( nowHref.replace(/^.*\/(m)\/.*$/,'$1') == "m" && memoLoadingA){
      memoLoading.innerHTML = "评论加载中……"
    }
    if( nowHref.replace(/^.*\/(m)\/.*$/,'$1') == "m" && !twikooDom){
      addTwikooJS()
      if(memoTw){
        clearInterval(start)
        memoTw.insertAdjacentHTML('afterend', '<div id="mtcomment"></div>');
        setTimeout(function() {
          twikoo.init({
            envId: twikooENV,
            el: '#mtcomment',
            path: nowHref.replace(/^(.*\/m\/[0-9]+).*$/,'$1'),
            onCommentLoaded: function () {
              //console.log('评论加载完成');
              memoLoading.innerHTML = ''
              startTwikoo()
            }
          })
        }, 1000)
      }
    }
    if(nowHref.replace(/^.*\/(explore).*$/,'$1') == "explore" || nowHref.replace(/^.*\/(u).*$/,'$1') == "u"){
      memoTwIcons.forEach(memoTwIcon => {memoTwIcon.remove();});
      addComIcon()
      //console.log('图标添加成功');
    }
    //console.log(window.location.href);
  }, 1000)
}
startTwikoo();
```

## 自定义样式

```
#twikoo{padding: 1rem;background-color: rgb(63,63,70);margin: 1rem 0;border-radius: .5rem;color: #fff !important;}
.twicon{position: absolute;right: 1rem;}
.btns-container.space-x-2{margin-right:1.5rem;}
.action-button-container{color: #e5e7eb;}
.action-button-container a{display:none !important;}
```