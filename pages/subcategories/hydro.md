---
layout: page
title: Гидронимы Краснодарского края и Республики Адыгея
subtitle: Водные объекты Кубани
cover-img: ["/img/example-logos/main-cover.jpg" : "Генеральная карта Кавказского края, изданная в 1858 г."]
share-img: /img/example-logos/main-cover4x3.jpg
share-title: "Реки Кубани: имена и тайны"
share-description: "Откуда взялись названия рек Кубани? Откройте для себя тайны гидронимов и погрузитесь в историю региона."
language: ru
keywords: карты, история, география, ономастика, гидроним
last_modified_at: 2024-11-18 20:00:00 +0300
date: 2022-01-14 16:00:00
permalink: /toponymy/hydro/
head-extra: [amp_link.html, etc/_aboutme.html, ads/ads.html, etc/_micro_hydro.html]
footer-extra: [ads/ads-footer.html]
---
Термин **гидроним** состоит из двух греческих слов, означающих _вода_ + _имя_ (название водных объектов), один из классов топонимов (географических названий), изучающих название водных объектов: рек, озёр, проливов, заливов, морей, родников. На Кубани много рек, речек и речушек, в литературе можно найти различные цифры об их количестве от 7 до 13 тыс. Среди гидронимов Кубани преобладают реки.

<div class="posts-list">
  {% assign hydro = site.toponymy | where: "category", "hydro" %}
  {% for toponymy in hydro %}
  <article class="post-preview">

  <!--    {%- capture thumbnail -%}
        {% if toponymy.thumbnail-img %}
          {{ toponymy.thumbnail-img }}
        {% elsif toponymy.cover-img %}
          {% if toponymy.cover-img.first %}
            {{ toponymy.cover-img[0].first.first }}
          {% else %}
            {{ toponymy.cover-img }}
          {% endif %}
        {% else %}
        {% endif %}
      {% endcapture %}
      {% assign thumbnail=thumbnail | strip %}

      {% if site.feed_show_excerpt == false %}
      {% if thumbnail != "" %} -->
      <div class="post-image post-image-normal">
        <a href="{{ toponymy.url | absolute_url }}" aria-label="Thumbnail">
          <img src="{{ toponymy.url | absolute_url | replace:'.ru/','.ru/img/' | append: 'thumb.jpg' }}" alt="{{ toponymy.thumbnail-caption }}" title="{{ toponymy.thumbnail-caption }}">
        </a>
      </div>
  <!--    {% endif %}
      {% endif %} -->

    <a title="{{ toponymy.share-title }}" href="{{ toponymy.url | absolute_url }}">
      <h2 class="post-title">{{ toponymy.title }}</h2>

      {% if toponymy.subtitle %}
        <h3 class="post-subtitle">
        {{ toponymy.subtitle }}
        </h3>
      {% endif %}
    </a>

    <p class="post-meta">
      {% assign date_format = site.date_format | default: "%B %-d, %Y" %}
      Дата публикации {{ toponymy.date | date: date_format }}
    </p>

    {% if thumbnail != "" %}
    <div class="post-image post-image-small">
      <a href="{{ toponymy.url | absolute_url }}" aria-label="Thumbnail">
        <img src="{{ toponymy.url | absolute_url | replace:'.ru/','.ru/img/' | append: 'thumb.jpg' }}" alt="{{ toponymy.thumbnail-caption }}" title="{{ toponymy.thumbnail-caption }}">
      </a>
    </div>
    {% endif %}

    {% unless site.feed_show_excerpt == false %}
    {% if thumbnail != "" %}
    <div class="post-image post-image-short">
      <a href="{{ toponymy.url | absolute_url }}" aria-label="Thumbnail">
        <img src="{{ toponymy.url | absolute_url | replace:'.ru/','.ru/img/' | append: 'thumb.jpg' }}" alt="{{ toponymy.thumbnail-caption }}" title="{{ toponymy.thumbnail-caption }}">
      </a>
    </div>
    {% endif %}

    <div class="post-entry">
      {{ toponymy.description }}
      <a title="{{ toponymy.share-title }}" href="{{ toponymy.url | absolute_url }}" class="post-read-more">[Читать&nbsp;далее]</a>
    </div>
    {% endunless %}

                        {% if forloop.index == 5 %}
                        {% include ads/ads-cat-1.html %}
                        {% endif %}
                        {% if forloop.index == 15 %}
                        {% include ads/ads-cat-2.html %}
                        {% endif %}
                        {% if forloop.index == 25 %}
                        {% include ads/ads-cat-3.html %}
                        {% endif %}

    {% if site.feed_show_tags != false and toponymy.tags.size > 0 %}
    <div class="blog-tags">
      <span>Метки:</span>
      {% for tag in toponymy.tags %}
      <a href="{{ '/tags/' | absolute_url }}#{{- tag -}}">{{- tag -}}</a>
      {% endfor %}
    </div>
    {% endif %}

   </article>
  {% endfor %}
</div>
