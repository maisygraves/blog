<div class="nav">
    <ul class="nav">
        
        {% for item in site.data.nav.navigation %}        <li><h3>
            <a href="{{ item.link }}">{{ item.name }}</a>
        </h3></li>
        {% endfor %}
        
    </ul>
</div>