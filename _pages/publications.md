---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: false
---

{% if site.author.googlescholar %}
  <div class="wordwrap">You can find an updated list of my articles on <a href="{{site.author.googlescholar}}">my Google Scholar profile</a>.</div>
{% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}
