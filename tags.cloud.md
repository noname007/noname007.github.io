---
layout: page
title: Tags
permalink: /tags-cloud/
published: false
---

<div class="blog-tags"> 
    {% assign tags = site.tags | sort %}
    {% for tag in tags %}
    <a href="#{{ tag[0] | slugify }}" class="btn btn-default" style="font-size: {{ tag | last | size  |  times: 4 | plus: 80  }}%"> 
	<!-- style="color: #1C1C1C;" is font color of cloud index -->
      <span class="fa fa-folder-open" aria-hidden="true"> 
        {{ tag[0] }}-<i class="badge">{{ tag | last | size }}</i>
      </span>
    </a>|
    {% endfor %}
  </div>
  <hr/> 
  <div class="post-preview"> 
    {% for tag in tags %} 
      <h2 id="{{ tag[0] | slugify }}" style="padding-top: 70px;"> {{ tag[0] }}-<i class="badge">{{ tag | last | size }}</i></h2>
      <ul class="later on">
        {% for post in tag[1] %}
          <a class="post-subtitle" href="{{ site.baseurl }}{{ post.url }}">
        <li>
          {{ post.title }}
        <small class="post-meta"> - Posted on {{ post.date | date: "%B %-d, %Y" }}</small>
        </li>
        </a>
        {% endfor %}
      </ul>
        <a href="#top" class="btn btn-default">
          <span class="fa fa-refresh" aria-hidden="true"></span> Go back to the top
        </a> 
        <hr/>
    {% endfor %}
  </div>
