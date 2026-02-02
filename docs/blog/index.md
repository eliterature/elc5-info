---
layout: blog
title: Blog
---

Stay up to date with the latest news and updates about the Electronic Literature Collection Volume 5.

{% assign posts = site.pages | where_exp: "page", "page.path contains 'blog/'" | where_exp: "page", "page.name != 'index.md'" | sort: "date" | reverse %}

{% for post in posts %}
  {% if post.title %}
  <article class="blog-post-preview">
    <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
    <p class="post-meta">
      <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time>
      {% if post.author %} • {{ post.author }}{% endif %}
    </p>
    {% if post.excerpt %}
    <p>{{ post.excerpt }}</p>
    {% endif %}
  </article>
  {% endif %}
{% endfor %}

---

Subscribe to our [RSS feed]({{ "/feed.xml" | relative_url }}) to stay updated.
