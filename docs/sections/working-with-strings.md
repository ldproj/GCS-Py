---
layout: section
title: Working With Strings
parent: Sections
permalink: section/working-with-strings
content_data: working-with-strings
nav_order: 4
---

{% assign pg_data = site.data.sections[page.content_data] %}

{% assign sections = pg_data.sections %}

{% comment %}
 this is the comment block

{% endcomment %}

{% for section in sections %}

{%- assign to_go = forloop.rindex -%}

{% if section.heading %}

{%- assign current = forloop.index | divided_by: 2 -%}
{%- assign current_id = current | plus: 1 -%}
{%- assign current_link = current | plus: 1 -%}
{%- assign up_link = current -%}
{%- assign down_link = current | plus: 2 -%}

{%- if to_go == 2 -%}
{%- assign last = true -%}
{%- endif -%}

{% include anchor-marker.html current_id=current_id current_link=current_link up_link=up_link down_link=down_link last=last  %}
{% assign heading = section.heading %}
{%- include item-heading.html heading=heading -%}
{% endif %}

{%- if section.body -%}
{% assign item = section %}
{% include item-body.html item=item %}
{% endif %}

{% endfor %}

{% comment %}
  This is a comment!
{{ section.heading }}
{: .fw-4 .text-grey-dk-100 }
>{{ section.body }}
{: .fs-2 }
{% endcomment %}
