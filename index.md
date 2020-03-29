---
title: "Metzgerei König Düsseldorf"
---

# Metzgerei König Düsseldorf

Lessingstrasse 29<br />
40227 Düsseldorf

* Tel: <a href="tel:+49211786777">0211 78 67 77</a>
* <a href="https://www.yelp.de/map/metzgerei-k%C3%B6nig-d%C3%BCsseldorf">Wegbeschreibung</a>
* <a href="https://www.yelp.de/biz/metzgerei-könig-düsseldorf">Bewertet uns auf Yelp</a>

## Speiseplan

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
		<th>Preis</th>
	</tr>
	</thead>
	<tbody>
	{% endif %}
	<tr>
		<td>
			 {{- site.data.week[todaysMenu.day].name -}}
		</td>
		<td>
			{%- assign dishes = todaysMenu.dish | split: "+" -%}
			{% for dish in dishes -%}
				{% assign theDish = site.data.dishes[dish] -%}
				{{ theDish.name }}{% if forloop.index != forloop.length %}<br/>{% endif %}
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

## Allergie Info

todo