# books
Book readings [books.csv]({{ site.github.repository_url }}/blob/master/_data/books.csv)  
build ``{{ site.github.build_revision }}``

{% for book in site.data.books %}- **`{{ book.Title }}`** {{ book.Author }} ({{ book.Start | date: "%B %-d %Y" }})  
{% endfor %}

<script type="text/javascript">
document.querySelector('body').classList.add('markdown-body');
</script>
