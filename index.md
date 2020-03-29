---
title: "Speiseplan Metzgerei König"
menuStart: "2020-03-30"
menuEnd: "2020-04-30"
---
{%- assign menuPeriod = page.menuStart | append: " - " | append: page.menuEnd -%}
# Speiseplan Metzgerei König

Bestellungen via Telefon: **<a href="tel:+49211786777">0211 78 67 77</a>**

* <a href="https://www.yelp.de/map/metzgerei-k%C3%B6nig-d%C3%BCsseldorf">Wegbeschreibung (via Yelp)</a>
* <a href="https://www.yelp.de/biz/metzgerei-könig-düsseldorf">Bewertet auf Yelp</a>

## Speiseplan für {{ page.menuStart | date: "%d.%m.%y"  }} bis {{ page.menuEnd  | date: "%d.%m.%y"  }}

<table>
{% for todaysMenu in site.data.menu %}
	{% if todaysMenu.week == menuPeriod %}
		{%- assign day = todaysMenu.day -%}
		{%- if forloop.index == 1 %}
		<thead>
			<tr>
				<th>Tag</th>
				<th>Gericht</th>
				<th>Info</th>
				<th>Preis</th>
			</tr>
		</thead>
		<tbody>
		{%- endif %}
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
				<!-- price -->
				<td>&euro;{{ todaysMenu.price }}</td>
			</tr>
		{% if forloop.index == forloop.length %}
		</tbody>
		{% endif %}
	{% else %}
	<tr><td>Keine Gerichte heute</td></tr>
	{% endif %}
{% endfor %}
</table>

### Alle Speisen können Spuren enthalten von:

<ul class="flat-list smaller">
{% for allergen in site.data.allergens %}
	<li>{{ allergen.id }}) {{ allergen.name }}</li>
{% endfor %}
</ul>

Bei weitere Fragen kontaktieren Sie bitte Metzgerei König via Telefon auf die <a href="tel:+49211786777">0211 78 67 77</a>.

## Öffnungszeiten

 Metzgerei König in Düsseldorf hat durchgehend geöffnet!

<table>
	{% for _day in site.data.openinghours %}
	<tr>
		<td>{{- site.data.week[_day.day].name -}}</td>
		<td>{{- _day.from -}}</td>
		<td>{{- _day.to -}}</td>
	</tr>
	{% endfor %}
</table>

## Zugang über Mobiltelefon

Scannen Sie das Bild mit Ihrem Handy ein, um einen direkten Zugang zu die Metzgerei König Website zu erhalten.

<figure class="qrcode">
	<a href="assets/img/qr-metzgereikonigd.svg">
		<img src="assets/img/qr-metzgereikonigd.svg" title="QR code für diese Website" alt="QR Code für https://metzgereikonigdusseldorf.github.io/speiseplan/" />
	</a>
	<figcaption>https://metzgereikonigdusseldorf.github.io/speiseplan/</figcaption>
</figure>

---

<div class="smaller">
	<h2>Haftungsausschluss</h2>
	<p>Die Informationen auf die Metzgerei König aus Düsseldorf Website können ohne vorherige Ankündigung geändert werden.</p>
	<h2>Datenschutzerklärung</h2>
	<p>Die Metzgerei König Website verwendet keine Cookies und verfolgt Sie nicht.</p>
	<p><a href="mailto:webmaster@johanbove.info?subject=Speiseplan%20Metzgerei%20König">Webmaster kontaktieren</a></p>
	<p>Letze Aktualisierung: 2020-03-29 23:21</p>
</div>