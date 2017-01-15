# books
Book readings

{% for book in site.data.books %}
- `{{ book.Title }}` {{ book.author }}
{% endfor %}
