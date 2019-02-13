---
layout: default
title: Ordlista 19

---

<div style="width: 100%;">


<div class="filter-row">

{% assign foo = "" %}

{% for website in site.websites %}

    {% assign foo = foo | append: website.metatags | append:"," %}

{% endfor %}

{% assign my_array = foo | remove: " " | split: "," %}
{% assign my_array = my_array | uniq %}

<ul class="tagfilter">
	<li class="tag-all"><input type="checkbox" name="all" value="all" checked="checked" class="allcheckbox" />All</li>
{% for tag in my_array %}
	<li class="tag-button"><input type="checkbox" name="{{ tag }}" value="{{ tag }}" class="filtercheckbox" /><span>{{ tag }}</span></li>
{% endfor %}
</ul>
</div>

	<div class="mainlist grid">
		{% for website in site.websites %}

    <a href="{{ website.permalink }}">

		 	<div class="websiteitem grid-item" data-tags="{{website.metatags}}">

		 		<img class="grid-item--image u-objectfit--cover" src="/siteimages/{{ website.permalink | remove: "/" }}.jpg" />

          <div class="grid-item_information-container">

  		      <h2 class="website website-title"><a href="{{ website.permalink }}">{{ website.title }}</a></h2>

  		        <p class="website-desc">{{ website.metadescription }}</p>

  		      <a href="{{ website.permalink }}">Läs mer om: {{ website.title }}</a>

          </div>

 	</div>

		{% endfor %}
