# books
Book readings [books.csv]({{ site.github.repository_url }}/blob/master/_data/books.csv)  
build ``{{ site.github.build_revision }}``

{% for book in site.data.books %}{% assign currentdate = book.Start | date: "%Y" %}{% if currentdate != date %}
## {{ currentdate }}
{% assign date = currentdate %}{% endif %}- **`{{ book.Title }}`** {{ book.Author }} <span class="text-gray-light">{{ book.Start | date: "%B %-d" }}</span>  
{% endfor %}

<script type="text/javascript">
document.querySelector('body').classList.add('markdown-body');
</script>
