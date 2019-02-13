---
layout: default
title: Ordlista 19

---

<div style="width: 100%;">



{% assign foo = "" %}

{% for website in site.websites %}

    {% assign foo = foo | append: website.metatags | append:"," %}

{% endfor %}

{% assign my_array = foo | remove: " " | split: "," %}
{% assign my_array = my_array | uniq %}

<ul class="tagfilter">
	<li class="tag-all"><input type="checkbox" name="all" value="all" checked="checked" class="allcheckbox" />All</li>
{% for tag in my_array %}
	<li class="tag-button"><input type="checkbox" name="{{ tag }}" value="{{ tag }}" class="filtercheckbox" />{{ tag }}</li>
{% endfor %}
</ul>

	<div class="mainlist">
		{% for website in site.websites %}
		 	<div class="websiteitem" data-tags="{{website.metatags}}">
		 		<img src="/siteimages/{{ website.permalink | remove: "/" }}.jpg" />
		      <h2 class="website"><a href="{{ website.permalink }}">{{ website.title }}</a></h2>
		        <p>{{ website.metadescription }}</p>
		      <a href="{{ website.permalink }}">Läs mer om: {{ website.title }}</a>
		 	</div>

		{% endfor %}
	</div>
</div>

