---
permalink: / # Needed on localhost
---
# books
- Repository: [{{ site.github.repository_url }}]({{ site.github.repository_url }})
- This page: [{{ site.github.repository_url }}/blob/master/{{ page.path }}]({{ site.github.repository_url }}/blob/master/{{ page.path }})
- Books file: [{{ site.github.repository_url }}/blob/master/_data/books.csv]({{ site.github.repository_url }}/blob/master/_data/books.csv) - {{ site.data.books | size }} items
- Build: ``{{ site.github.build_revision }}`` - {{ site.time | date: "%Y %B %-d %H:%M" }}
- Format: #. **Book title** - <span class="text-red">Author</span> - <span class="text-gray-light">Start reading (days)</span>

{% for book in site.data.books %}{% assign Year = book.Start | date: "%Y" %}{% assign newYear = Year | prepend: "01-01-" | date: "%s" %}{% assign Start = book.Start | date: "%s" %}{% assign index = forloop.index0 | minus: 1 %}{% assign End = site.data.books[index].Start %}{% assign End = End | date: "%s" %}{% assign Duration = End | minus: Start %}{% assign Days = Duration | divided_by: 86400.0 %}{% if Year != currentYear %}
## {{ Year }}
{% assign currentYear = Year %}{% assign newYear = Year | prepend: "01-01-" | date: "%s" %}{% assign End = Year | prepend: "31-12-" | date: "%s" %}{% assign Duration = End | minus: Start %}{% endif %}1. <span class="bar"><span style="width: {{ Start | minus: newYear | times: site.bar.width | divided_by: 31536000.0 }}em;"></span>{% unless forloop.first %}<span class="range" style="width: {{ Duration | times: site.bar.width | divided_by: 31536000.0 }}em;"></span>{% endunless %}</span> **{{ book.Title }}** - <span class="text-red">{{ book.Author }}</span> - <span class="text-gray-light">{{ book.Start | date: "%B %-d" }}{% unless forloop.first %} ({{ Days | ceil }}){% endunless %}</span>
{% endfor %}

<style media="screen">
span{
  display: inline-block;
	height: .7em;
}
span.bar{
  width: {{ site.bar.width }}em;
	margin: 0 0.5em;
  border-bottom: 1px solid lightgrey;
}
span.range{
	background-color: lightgrey;
}
</style>

<script type="text/javascript">
document.querySelector('body').classList.add('markdown-body');
</script>
