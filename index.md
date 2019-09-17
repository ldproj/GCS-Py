---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: Home
nav_order: 1
---

<!--
bring in the data for the content
 -->

{% assign pg_data=site.data.pages.index %}

<!--
data for list of all posts
-->
{% assign items=pg_data.new_items %}

<!--
add the most recent item at the top
-->
NEW
{: .label .label-green }
{% assign heading=items[0]['heading'] %}
{{ heading }}
{: .fs-8 .text-purple-200}
{% assign description=items[0]['description'] %}
{{ description }}
{: .fs-4 .text-blue-200}

<!--
add the big button
 -->
{% assign target=pg_data.big_button.link %}
{% include big-button.html target=target  %}

<!--
loop to add the rest of the items
-->
{% for item in items %}
{% if forloop.index0 != 0 %}
{% include post-item.html item=item %}
{% endif %}
{% endfor %}

<!--
add the other buttons
[Sections]({{site.baseurl}}sections/){: .btn .btn-purple }
[Resources]({{site.baseurl}}resources/){: .btn .btn-blue }
[References]({{site.baseurl}}references/){: .btn .btn-green }
 -->
