# books
- Repository: [{{ site.github.repository_url }}]({{ site.github.repository_url }})
- This page: [{{ site.github.repository_url }}/blob/master/{{ page.path }}]({{ site.github.repository_url }}/blob/master/{{ page.path }})
- Books file: [{{ site.github.repository_url }}/blob/master/_data/books.csv]({{ site.github.repository_url }}/blob/master/_data/books.csv) - {{ site.data.books | size }} items
- Build: ``{{ site.github.build_revision }}`` - {{ site.time | date: "%Y %-d %B %H:%M" }}
- Format: #. **Book title** - <span class="text-red">Author</span> - <span class="text-gray-light">Start reading</span>

{% for book in site.data.books %}{% assign currentdate = book.Start | date: "%Y" %}{% if currentdate != date %}
## {{ currentdate }}
{% assign date = currentdate %}{% endif %}1. **{{ book.Title }}** - <span class="text-red">{{ book.Author }}</span> - <span class="text-gray-light">{{ book.Start | date: "%B %-d" }}</span>  
{% endfor %}

<script type="text/javascript">
document.querySelector('body').classList.add('markdown-body');
</script>
