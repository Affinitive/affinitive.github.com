---
layout: default
tagline: Supporting tagline
---

{% include JB/setup %}
{{ theme.name }}
{% assign site.theme.showNav = false %}
{% for post in site.posts %}
<div class="post h-entry">
  {% include themes/affinitivedev/innerPost %}
</div>
{% endfor %}


