---
title: Index
undefined: SUB TITLE
date: 2018-07-28 04:46:38 +0000
ttitle: ''
banner_post: ''
tag: []

---
<div class="blog-index">  
  {% assign post = site.posts.first %}
  {% assign content = post.content %}
  {% include post_detail.html %}
</div>