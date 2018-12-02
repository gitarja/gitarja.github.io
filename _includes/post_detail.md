
{% for post in site.categories.bahasa %}
   <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
   <p><small><strong>{{ post.date | date: "%B %e, %Y" }}</strong> . {{ post.category }} . <a href="{{ root_url }}{{ post.url }}"></a></small></p>
{% endfor %}
