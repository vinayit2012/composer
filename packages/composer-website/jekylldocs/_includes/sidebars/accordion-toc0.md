{% assign sorted = site.pages | sort: 'index-order' %}
{% for page in sorted %}
{% if page.index-order %}
{% capture mods %}{{ page.index-order | modulo:100 }}{% endcapture %}
{% if mods == "0" and page.exception == nil %}
- [<b>{{ page.title }}</b><img src="{{site.baseurl}}/assets/img/Caret_SW_2.svg" class="caret">]({{site.baseurl}}{{page.url}})
{% elsif mods != "0" and page.exception == nil %}
  - [{{page.title}}]({{site.baseurl}}{{page.url}})
{% endif %}
{% endif %}
{% endfor %}
