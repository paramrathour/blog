---
title: Manga Reading Timeline
subject: "Unveiling my manga journey: thoughts and timeline"
date: 2023-12-13
categories: [Animanga, Timeline]
tags: [manga, timeline, thoughts]
---
I suggest reading [my anime timeline](/blog/anime-timeline) before this blog. Thus, there's no need to again go over the specifics here.

## Motivation
I don't classify myself as an avid manga reader, my usual go-to is checking out the manga versions of ongoing anime that leave me itching to know what happens next.

## Personal Insights
Like before, you can hover over the names (or long-press for mobile users) to uncover my thoughts (mostly spoiler-free) on each manga.

## Timeline
Alright, let's dive right in!

<style>
  .tooltip-inner{
    font-size: 0.8rem;
    max-width: 543px;o
    text-align: left;
  }
</style>

{% include lang.html %}

{% assign df_strftime_m = site.data.locales[lang].df.archives.strftime | default: '/ %m' %}
{% assign df_dayjs_m = site.data.locales[lang].df.archives.dayjs | default: '/ MM' %}

<div id="archives" class="pl-xl-3">
  {% for post in site.manga %}
    {% assign cur_year = post.date | date: '%Y' %}

    {% if cur_year != last_year %}
      {% unless forloop.first %}</ul>{% endunless %}

      <time class="year lead d-block">{{ cur_year }}</time>
      {{ '<ul class="list-unstyled">' }}

      {% assign last_year = cur_year %}
    {% endif %}

    <li>
      {% assign ts = post.date | date: '%s' %}
      <span class="date day" data-ts="{{ ts }}" data-df="DD">{{ post.date | date: '%d' }}</span>
      <span class="date month small text-muted ms-1" data-ts="{{ ts }}" data-df="{{ df_dayjs_m }}">{{ post.date | date: df_strftime_m }}</span>
      <a href="{{ 'https://myanimelist.net/manga/' | append: post.code }}" data-bs-toggle="tooltip" data-bs-placement="right" data-bs-html="true" title = "{{ post.content }}">{{ post.title }}</a>
    </li>

    {% if forloop.last %}</ul>{% endif %}
  {% endfor %}
</div>