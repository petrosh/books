# books
Book readings

{% for book in site.data.books %}- **`{{ book.Title }}`** {{ book.Author }}  
{% endfor %}

<script type="text/javascript">
document.querySelector('body').classList.add('markdown-body');
</script>
