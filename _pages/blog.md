---
layout: no-header
hide_header: true
permalink: /cmudrlrg/
title: CMU DRL RG
nav: true
nav_order: 1
# pagination:
#   enabled: true
#   collection: topics
#   permalink: /page/:num/
#   per_page: 5
#   sort_field: date
#   sort_reverse: true
#   trail:
#     before: 1 # The number of links before the current page
#     after: 3 # The number of links after the current page
---

<div class="post">

{% assign blog_name_size = site.blog_name | size %}
{% assign blog_description_size = site.blog_description | size %}

{% if blog_name_size > 0 or blog_description_size > 0 %}

  <div class="header-bar">
    <h1>{{ site.blog_name }}</h1>
    <div class="description">
      {{ site.blog_description | markdownify }}
    </div>
  </div>
  {% endif %}

  <div class="cmudrlrg-header d-flex justify-content-between align-items-center mb-3">
    <h2>TOPICS</h2>
    <!-- You can add sort/filter controls here later -->
  </div>

  <ul class="custom-topic-list list-unstyled">
    {% assign postlist = site.drltopics | sort: 'date' %}
    {% for post in postlist %}
      <li class="mb-5 pb-3 border-bottom">
        <div class="d-flex justify-content-between align-items-start">
          <div class="text-muted" style="min-width: 120px;">
            <strong>Week {{ post.week }}</strong><br>
            {{ post.date | date: "%b %e, %Y" }}
          </div>
          <div class="flex-grow-1 ms-3">
            <h4 class="mb-1">
              {{ post.title }}
            </h4>
            <p class="mb-2">
              {{ post.description }}
            </p>
            {% if post.links %}
              <div class="resource-links small">
                {% for link in post.links %}
                  <a href="{{ link.url }}" class="me-2">{{ link.label }}</a>
                  {% unless forloop.last %} • {% endunless %}
                {% endfor %}
              </div>
            {% endif %}
          </div>
        </div>
      </li>
    {% endfor %}
  </ul>


  <div class="cmudrlrg-header d-flex justify-content-between align-items-center mb-3">
    <!-- <h2>ORGANIZERS</h2> -->
    <!-- You can add sort/filter controls here later -->
  </div>
  <div class="organizers">
    <p>This is being run by me, <a href="https://neeleshbisht99.github.io/" target="_blank">Neelesh</a> 
    (<a href="https://x.com/neelbisht99" target="_blank">neelbisht99</a>)
    Join <a href="mailto:nbisht@andrew.cmu.edu">CMUDRLRG</a>
    </p> 
  </div>
</div>
