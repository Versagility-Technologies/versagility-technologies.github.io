---
title: Get to know the team
excerpt: So...who are we?
tags: featured
categories:
  - topics
background-image: iphone-notebook.jpg
icon: users
#date/lastmod are optional
#date: 2020-02-06 12:10:51 -0500
#lastmod: 2020-02-06 12:10:51 -0500
team:
  - mike
  - derek
  - brad
  - pat
  - tan
---

<div class="row">
  <div class="col-md-4" markdown="1">
  <img height="100px" class="center-block" src="../images/logo.png">
  </div>
  <div class="col-md-8" markdown="1">
  {{ site.closing-para }}
  </div>
</div>

{% for member in page.team %}
{% assign auth = site.data.authors[member] %}
{% assign test1 = auth.avatar | slice: 0,4 %}
{% if test1 == "http" %}
{%   assign pic = auth.avatar %}
{% else %}
{%   assign pic = auth.avatar | prepend: "/images/" | prepend: site.baseurl %}
{% endif %}
<div class="author" style="margin-bottom:10px">
  {% if auth.avatar == "" %}
  <div style="display:inline-block;border-radius:7px;overflow:hidden;height:100px;width:100px;background-size:100px;"><span class="icon fa-user styleN"></span></div>
  {% else %}
  <div style="display:inline-block;border-radius:7px;overflow:hidden;height:100px;width:100px;background:url({{ pic }});background-size:100px;"></div>
  {% endif %}
  <div style="display:inline-block;padding-left:5px;vertical-align:top;"><b>{{
    auth.name }}</b>{% if auth.email %}<br />(<a href="mailto:{{ auth.email }}">{{ auth.email }}</a>){% endif %}<br
    /><i><a href="{{ auth.url }}" target="_blank">{{ auth.url }}</a></i>
  </div>
  <div class="auth-desc">{{ auth.bio }}</div>
</div>
{% endfor %}