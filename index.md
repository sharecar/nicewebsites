---
layout: default
title: Ordlista 19

---

<div style="
  width: 100%;
">


 {% for website in site.websites %}
 	<div>
 		<img src="/siteimages/{{ website.permalink | remove: "/" }}.jpg" />
      <h2 class="website"><a href="{{ website.permalink }}">{{ website.title }}</a></h2>
        <p>{{ website.metadescription }}</p>
      <a href="{{ website.permalink }}">Läs mer om: {{ website.title }}</a>
 	</div>

 {% endfor %}

</div>

