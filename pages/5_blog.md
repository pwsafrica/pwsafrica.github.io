---
layout: page
title: Blog
permalink: /blog/	
subtitle: "<hr> Read about our experience running PWSAfrica." 
feature-img: "assets/img/pexels/computer2.jpeg"
---

<link rel="stylesheet" href="/assets/css/style.css">


  <div class="posts">
    {% for post in site.posts %}
    <div class="post-teaser">
      {% if post.thumbnail %} 
      <div class="post-img">
         <img src="{{ site.baseurl }}/{{ post.thumbnail }}">
      </div>
      {% endif %}
      <span>
          <header style="color:#262626">
            <h1 style="color:black">
              <a class="p-header" href="{{ post.url | prepend: site.baseurl }}">
                {{ post.title }}
              </a>
            </h1>
            <p class="meta" style="color:#383838;">
              {{ post.date | date: "%B %-d, %Y" }}
            </p>
          </header>
          <div class="excerpt">
              {{ post.excerpt | strip_html | escape }}
            <!--{{ post.content | strip_html | truncate: "250" }}-->
            <!--<a class="button" href="{{ post.url | prepend: site.baseurl }}">
              {{ site.theme_settings.str_continue_reading }}
            </a>-->
          </div>
      </span>
    </div>
    {% endfor %}
  </div>

  {% if paginator.total_pages > 1 %}
  <div class="pagination">
    {% if paginator.previous_page %}
    <a href="{{ paginator.previous_page_path | prepend: site.baseurl | replace: '//', '/' }}" class="button" >
      <i class="fa fa-chevron-left"></i>
      {{ site.theme_settings.str_previous_page }}
    </a>
    {% endif %}
    {% if paginator.next_page %}
    <a href="{{ paginator.next_page_path | prepend: site.baseurl | replace: '//', '/' }}" class="button" >
      {{ site.theme_settings.str_next_page }}
      <i class="fa fa-chevron-right"></i>
    </a>
    {% endif %}
  </div>
  {% endif %}
