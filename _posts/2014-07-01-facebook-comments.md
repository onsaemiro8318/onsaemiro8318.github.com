---
layout: post
title: "GitHub 블로그에 페이스북 댓글 연동하기"
description: ""
category: study
tags: [facebook comments]
---
{% include JB/setup %}

###댓글 연동했는데 글마다 같은 댓글

블로그는 하나의 Post가 각각의 URL을 갖기 때문에 URL에 따라 각각 댓글을 다르게 관리해야 한다.

github 블로그 프로젝트 파일 중에서 _includes > JB > comments-providers 폴더 내 facekbook 파일 내용을 아래와 같이 해주면 된다.

data-href="" 부분에 {{ site.production_url }} 이것만 넣게 되면 글마다 댓글이 구분되지 않고 블로그 전체 통합댓글이 되어버린다.

{{ site.production_url }}{{ page.url }} 이렇게 page.url도 같이 넣어줘야 각 포스트별로 댓글이 구분된다.

~~~
<div id="fb-root"></div>
<script>(function(d, s, id) {
  var js, fjs = d.getElementsByTagName(s)[0];
  if (d.getElementById(id)) return;
  js = d.createElement(s); js.id = id;
  js.src = "//connect.facebook.net/en_US/all.js#xfbml=1&appId={{ site.JB.comments.facebook.appid }}";
  fjs.parentNode.insertBefore(js, fjs);
}(document, 'script', 'facebook-jssdk'));</script>
<div class="fb-comments" data-href="{{ site.production_url }}{{ page.url }}" data-num-posts="{{ site.JB.comments.facebook.num_posts }}" data-width="{{ site.JB.comments.facebook.width }}" data-colorscheme="{{ site.JB.comments.facebook.colorscheme }}"></div>
~~~