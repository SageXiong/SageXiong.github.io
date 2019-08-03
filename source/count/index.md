---
title: 琅琊榜
date: 2018-12-27 20:24:50
comments: false
---

<blockquote class="blockquote-center">琅琊榜首，江左梅郎</blockquote>

<p id="heheda"><font size="4">阅读琅琊榜Top：<br><br></font></p>

<script src="https://cdn1.lncld.net/static/js/av-core-mini-0.6.1.js"></script>

<script>AV.initialize("p2tw72XaLbwCDYrtosjdIVW9-gzGzoHsz", "UHaUjoUGaeuoLOvSdkyQIU0P");</script>

<script type="text/javascript">
  var num=30 //最终只返回n条结果
  var time=0
  var title=""
  var url=""
  var query = new AV.Query('Counter');//表名
  query.notEqualTo('id',0); //id不为0的结果
  query.descending('time'); //结果按阅读次数降序排序
  query.limit(num);  
  query.find().then(function (todo) {
	debugger;
    for (var i=0;i<num;i++){ 
      console.log(todo[i]);
      var result=todo[i].attributes;
      time=result.time;  //阅读次数
      title=result.title; //文章标题
      url=result.url;     //文章url
      console.log(title);
      console.log(url);
      console.log(time);
      var content="<p>"+"【阅读次数:"+time+"】"+"<a href='"+"https://sagexiong.github.io/"+url+"'>"+"<font color='#0477ab'>"+title+"</font>"+"</a>"+"</p>";
      // document.write("<a href='"+"https://sagexiong.github.io/"+url+"'>"+title+"</a>"+"    Readtimes:"+time+"<br>");
      document.getElementById("heheda").innerHTML+=content
    }
  }, function (error) {
    console.log("error");
  });
</script>
