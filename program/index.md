---
layout: page
title: Program
excerpt: "Program"
---

## Program
{: class="center" }

Learn about the [Open Space format](/general/open-space-format) & [Ignite talks](/general/ignite-talks-format)

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
                    <h3 class="day-title">Day {{ post.day }}, {{ day }}</h3>
                </article>
                {% assign confDay = day %}
            {% endif %}
            {% if post.accepted == true %}
                <article class="session">            
                    <ul class="session-info">
                        <li class="session-time">
                            {{ post.start }}
                        </li>
                        <li class="session-title">
                            <a href="{{ post.permalink }}">{{ post.title }}</a>
                        </li>
                        {% if post.presenters != null %}
                        <li class="session-presenters">
                            <span class="presenters">by {{ post.presenters }}</span>
                        </li>
                        {% endif %}
                    </ul>
                </article>
            {% endif %}
        {% endfor %}
        <article class="session"></article>
    </section>  
</div>


