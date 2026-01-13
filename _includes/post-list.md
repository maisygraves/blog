<ul class="post-list">
    <ul class="post-list">
        <li>
            {{ post.date | date: "%Y-%m-%d" }}
        </li>
        <li>
            <h2 style="text-indent: 2rem;"><a href="{{ post.url }}">{{ post.title }}</a></h2>
        </li>
    </ul>

    <li class="post-subheading-skills">
        {% for skills in post.skills %}
            <a href="/skills/{{ skills }}/">/{{ skills }}</a>
        {% endfor %}
    </li>

</ul>

