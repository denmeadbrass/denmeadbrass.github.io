---
layout: page
title: "Hear Denmead Brass Play"
---

Come and hear Denmead Brass play live at one of our upcoming public appearances. We play music in all sorts of styles from film, shows, pop, jazz, classical, as well as traditional brass band music.

Blah blah

<div class="columns is-multiline">
    {% assign sorted = site.posts 
    | where_exp: "x", "x.categories contains 'gigs' or x.category == 'gigs'" 
    | sort: 'date' %}
    {% capture now %}{{"now" | date: "%s" | plus: 0 }}{% endcapture %}
    {% for post in sorted %}    
    {% capture post_date %}{{post.date | date: "%s" | plus: 0 }}{% endcapture %}
        {% if post_date >= now %}
        <div class="column is-half">
          <a href="{{ post.url }}">
            {% include gigcard.html %}
          </a>
        </div>
        {% endif %}
    {% endfor %}
</div>