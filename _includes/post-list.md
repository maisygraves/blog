<li class="post-item">
    
    {{ post.date | date: "%Y-%m-%d" }}

    <h2 class="post-title"><a href="{{ post.url }}">{{ post.title }}</a></h2>

    <span class="post-tags">
        {% for tag in post.tags %}

            <a class="tag" href="/tags/{{ tag }}/">.{{ tag }}</a>

        {% endfor %}
    </span>
</li>