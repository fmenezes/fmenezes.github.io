{% for post in site.posts %}
<small>{{ post.date | date: "%-d %B %Y" }}</small>
## [{{ post.title }}]({{ post.url }})
{{ post.content }}
{% endfor %}
