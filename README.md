# books
- Repository: [{{ site.github.repository_url }}]({{ site.github.repository_url }})
- Books file: [books.csv]({{ site.github.repository_url }}/blob/master/_data/books.csv)
- build: ``{{ site.github.build_revision }}``

{% for book in site.data.books %}{% assign currentdate = book.Start | date: "%Y" %}{% if currentdate != date %}
## {{ currentdate }}
{% assign date = currentdate %}{% endif %}- **{{ book.Title }}** • <span class="text-red">{{ book.Author }}</span> • <span class="text-gray-light">{{ book.Start | date: "%B %-d" }}</span>  
{% endfor %}

<script type="text/javascript">
document.querySelector('body').classList.add('markdown-body');
</script>
