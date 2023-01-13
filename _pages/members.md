---
layout: default
title: Members
permalink: /members/
description: 
nav: true
nav_order: 3
display_categories: [visiting, postdoc, phd, ms, undergrad, alumni-postdoc, alumni-phd, alumni-ms, alumni-undergrad, former-visiting]
---

<div class="members">
  
  <h2>Director</h2>
  {%- assign profs = site.members | where: "category", "prof" -%}
  {%- for prof in profs -%}
  <div class="container">
    <div class="row">
      <div class="col-4">
        {%- if prof.redirect -%}
        <a href="{{ prof.redirect }}" style="color:black;">
        {%- else -%}
        <a href="{{ prof.url | relative_url }}" style="color:black;">
        {%- endif -%} 
        {% assign image =  prof.img | prepend: "assets/img/members/" %}
        {% include figure.html class="img-fluid rounded" path=image alt="member thumbnail" %}
        </a>
      </div>
      <div class="col">
        <span style="color:black">  
        {%- if prof.redirect -%}
        <a href="{{ prof.redirect }}" style="color:black;">
        {%- else -%}
        <a href="{{ prof.url | relative_url }}" style="color:black;">
        {%- endif -%}
          <h5><b>Prof. {{ prof.name }}</b></h5>
        </a>
        </span>
        <hr style='margin-top:0.35em;margin-bottom:0.35em;' />
        {{ prof.content }}
      </div>
    </div>
  </div>
  {%- endfor %}

  <h2>Members</h2>
  <div class="container">
    <div class="row row-cols-4">
    {%- for category in page.display_categories %}
    {%- assign categorized_members = site.members | where: "category", category -%}
    {%- assign sorted_members = categorized_members | sort: "startyear" %}
    {%- for member in sorted_members -%}
      <div class="col">
      {% include members.html %}
      </div>
    {%- endfor %}
    {% endfor %}
    </div>
  </div>

</div>
