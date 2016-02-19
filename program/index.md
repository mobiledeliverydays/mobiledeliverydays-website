---
layout: page
title: Program
excerpt: "Program"
---

## Program
{: class="center" }

Learn about the [Open Space format](/general/open-space-format) & [Ignite talks](/general/ignite-talks-format)

*This is very much a work in progress. We're still working out the logistics.*

<div id="schedule">
    <section class="day">
    {% assign confDay = '' %}
    {% for post in site.categories.session reversed %}
      {% capture day %}{{ post.date | date: "%b %d" }}{% endcapture %}
      {% if confDay != day %}
        {% if confDay != '' %}
        <article class="session"></article>
      </section>
      <section class="day">
        {% endif %}
        <article>
          <h3 class="day-title">Day {{post.day}}, {{day}}</h3>
        </article>
        {% assign confDay = day %}
      {% endif %}
      {% if post.accepted == true %}
          <article class="session">
        		<h4 class="session-time">{{ post.start }}</h4>              
            <div class="session-info">
            	<h3><a href="{{ post.permalink }}">{{ post.title }}</a></h3>

            	{% if post.presenters != null %}
                <p class="meta">
              	  <span class="presenters">{{ post.presenters }}</span>
              	</p>
              {% endif %}

            </div>
          </article>
      {% endif %}
    {% endfor %}
    <article class="session"></article>
  	</section>  
</div>


