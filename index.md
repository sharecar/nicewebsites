---
layout: default
title: Ordlista 19

---

<div style="
  width: 100%;
">

 {% assign letter = "" %}
 {% for website in site.websites %}
 	{% assign foo = ord.title | slice: 0 %}

 	{% unless letter contains foo %}
		<a class="anchor" name="{{ website.title | slice: 0 }}">{{ website.title | slice: 0 }}</a>
 		<hr/>
 	{% endunless %}
 	{% assign letter = foo %}

 	<div>
      <h2 class="website"><a href="{{ website.permalink }}">{{ website.title }}</a></h2>
        <p>{{ website.metadescription }}</p>
      <a href="{{ website.permalink }}">Läs mer om: {{ website.title }}</a>
 	</div>

 {% endfor %}

</div>

