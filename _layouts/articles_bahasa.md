{% include header.html %}

<article>
<div class="container">
<div class="row">
<div class="col-md-8 col-md-offset-2">

  {%- if site.posts.size > 0 -%}


   {% for post in site.categories.bahasa %}
       {% assign currentDate = post.date | date: "%Y" %}
       {% if currentDate != myDate %}
           {% unless forloop.first %}</ul>{% endunless %}
           <h1>{{ currentDate }}</h1>
           <ul>
           {% assign myDate = currentDate %}
       {% endif %}
       <li><a href="{{ post.url }}"><span>{{ post.date | date: "%B %-d, %Y" }}</span> - {{ post.title }}</a></li>
       {% if forloop.last %}</ul>{% endif %}
   {% endfor %}



   
  {%- endif -%}

</div>
</div>
</div>
</article>

{% include footer.html %}