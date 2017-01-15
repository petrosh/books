# books
Book readings

{% for book in site.data.books %}- **`{{ book.Title }}`** {{ book.Author }} ({{ book.Start | date: "%B %-d %Y" }})  
{% endfor %}

<script type="text/javascript">
document.querySelector('body').classList.add('markdown-body');
</script>
