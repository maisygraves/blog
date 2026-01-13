<ul class="post-list">
    <ul class="post-list">
        <li>
            <ul class="post-list-date_category">
                <li>{{ post.date | date: "%Y-%m-%d" }}</li>
                <li class="post-list-_category">{{ post.category }}</li>
            </ul>
        </li>
        <li>
            <h2 class="post-list"><a href="{{ post.url }}">{{ post.title }}</a></h2>
        </li>
    </ul>

    <li class="post-subheading-skills">
        {% for skills in post.skills %}
            <a href="/skills/{{ skills }}/">/{{ skills }}</a>
        {% endfor %}
    </li>

</ul>

