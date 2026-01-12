<div class="nav">
    <ul class="nav">
        {% for item in site.data.nav.navigation %}        <li><h2><a href="{{ item.link }}">{{ item.name }}</a></h2></li>
        {% endfor %}
    </ul>
</div>