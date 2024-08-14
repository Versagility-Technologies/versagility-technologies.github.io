---
title: Get to know the team
excerpt: Discover how our combined strengths and varied backgrounds fuel innovation
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

{%   assign logo = "versagility-logo.png" | prepend: "/images/" | prepend: site.baseurl %}
<div class="row">
  <div class="col-md-4" markdown="1">
  <img class="center-block" src="{{logo}}">
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
  <div class="auth-info">
  {% if auth.avatar == "" %}
  <div style="display:inline-block;border-radius:7px;overflow:hidden;height:250px;width:250px;background-size:250px;"><span class="icon fa-user styleN"></span></div>
  {% else %}
  <div style="display:inline-block;border-radius:7px;overflow:hidden;height:250px;width:250px;background:url({{ pic }});background-size:250px;"></div>
  {% endif %}
  <br/>
  <div style="display:inline-block;padding-left:5px;"><b>{{
    auth.name }}</b>{% if auth.email %}<br />(<a href="mailto:{{ auth.email }}">{{ auth.email }}</a>){% endif %}<br
    /><i><a href="{{ auth.url }}" target="_blank">{{ auth.url }}</a></i><br/>
    {% if auth.credentials != blank %}
      <div style="width:300px;word-wrap: break-word">
      {% for cred in auth.credentials %}
        <a href="{{cred.url}}" target="_blank">
          {% assign credImg = cred.image | prepend: "/images/" | prepend: site.baseurl %}
          <div style="display:inline-block;border-radius:7px;overflow:hidden;height:50px;width:50px;background:url({{ credImg }});background-size:50px;" title="{{cred.text}}"></div>
        </a>
      {% endfor %}
      </div>
    {% endif %}
  </div>
  </div>
  <div class="auth-desc">{{ auth.bio }}</div>
</div>
<hr/>
{% endfor %}
