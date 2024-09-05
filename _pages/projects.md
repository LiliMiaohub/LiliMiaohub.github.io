---
layout: page
title: Podcast
permalink: /projects/
description:
nav: true
nav_order: 4
display_categories: [work, fun]
horizontal: false

---
I am a co-host of the Chinese podcast "Nothing to be Feared" (不以畏然). We want to accompany our listeners through sincere sharing. As our podcast advocates, we do not aim to understand many life principles; we simply wish to face each important moment without fearing love and not loving.

We welcome everyone to follow us on the Xiaoyuzhou app (小宇宙).

**Released Episodes**
- 08-29-2024 Olympic Memories: A New Narrative Under the Sunset Glow.
- 08-15-2024 Life is not about living a whole lifetime but about living for those few moments.
- 07-31-2024 Respecting yourself is the treatment for overcoming Asian trauma.
- 07-17-2024 The Hidden Pain of Mothers.
- 07-10-2024 Superstition, Astrology, and the Science Behind Them.
- 07-03-2024 How Did We Navigate the Low Point After the Breakup.



<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
