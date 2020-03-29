---
title: "Speiseplan Metzgerei König"
---

# Speiseplan Metzgerei König

Bestellungen via Telefon: **<a href="tel:+49211786777">0211 78 67 77</a>**

* <a href="https://www.yelp.de/map/metzgerei-k%C3%B6nig-d%C3%BCsseldorf">Wegbeschreibung (via Yelp)</a>
* <a href="https://www.yelp.de/biz/metzgerei-könig-düsseldorf">Bewertet auf Yelp</a>

<table>
{% for todaysMenu in site.data.menu %}
{%- assign day = todaysMenu.day -%}
	{% if forloop.index == 1 %}
	<thead>
	<tr>
		<th colspan="3">Speiseplan Woche: {{ todaysMenu.week }}</th>
	</tr>
	<tr>
		<th>Tag</th>
		<th>Gericht</th>
		<th>Info</th>
		<th>Preis</th>
	</tr>
	</thead>
	<tbody>
	{% endif %}
	<tr>
		<td>
			 {{- site.data.week[todaysMenu.day].name -}}
		</td>
		<!-- dish -->
		<td>
			{%- assign dishes = todaysMenu.dish | split: "+" -%}
			{% for dish in dishes -%}
				{% assign theDish = site.data.dishes[dish] -%}
				{{ theDish.name }}{% if forloop.index != forloop.length %}<br/>{% endif %}
			{%- endfor -%}
		</td>
		<!-- allergens -->
		<td class="smaller">
			{%- assign dishes = todaysMenu.dish | split: "+" -%}
			{% for dish in dishes -%}
				{% assign theDish = site.data.dishes[dish] -%}
				{{ theDish.allergens | replace: ",", ", " }}
				{% if forloop.index != forloop.length %}<br/>{% endif %}
			{%- endfor -%}
		</td>
		<td>&euro; {{ todaysMenu.price }}</td>
	</tr>
	{% if forloop.index == forloop.length %}
	</tbody>
	{% endif %}
{% else %}
<tr><td>Keine Gerichte heute</td></tr>
{% endfor %}
</table>

### Alle Speisen können Spuren enthalten von:

<ul class="flat-list smaller">
{% for allergen in site.data.allergens %}
	<li>{{ allergen.id }}) {{ allergen.name }}</li>
{% endfor %}
</ul>
