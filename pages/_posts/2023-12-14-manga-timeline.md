---
title: Manga Reading Timeline
description: "Unveiling my manga journey: thoughts and timeline"
date: 2023-12-14 07:59:05 +05:30
categories: [Animanga, Timeline]
tags: [manga, timeline, thoughts]
---
> I suggest reading [my anime timeline]({% post_url 2023-12-14-anime-timeline %}) before this blog. There's no need to go over the specifics again.
{: .prompt-tip }

## Motivation
I don't classify myself as an avid manga reader, my usual go-to is checking out the manga versions of ongoing anime that leave me itching to know what happens next.

## Personal Insights
Like before, you can hover/click on the comments icon to uncover my thoughts (mostly spoiler-free) on each manga. Mobile users may need to rotate their device to landscape mode to read comments for longer titles.

## Timeline
Alright, let's dive right in!

<style>
  .tooltip-inner{
    font-size: 0.8rem;
    max-width: 100%;
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

      <time id={{ cur_year }} class="year lead d-block">{{ cur_year }}</time>
      {{ '<ul class="list-unstyled">' }}

      {% assign last_year = cur_year %}
    {% endif %}

    <li id="{{ cur_year }}">
      {% assign ts = post.date | date: '%s' %}
      <span class="date day" data-ts="{{ ts }}" data-df="DD">{{ post.date | date: '%d' }}</span>
      <span class="date month small text-muted ms-1" data-ts="{{ ts }}" data-df="{{ df_dayjs_m }}">
        {{ post.date | date: df_strftime_m }}
      </span>
      <a href="{{ 'https://myanimelist.net/manga/' | append: post.code }}">{{ post.title }}</a>
      {% assign content = post.content | strip_newlines %}
      {% if content != "" %}
        <span data-bs-toggle="tooltip" data-bs-placement="top" data-bs-html="true" data-bs-trigger="hover focus" title = "{{ post.content }}"><i class="fa-fw fas fa-xs fa-comment"></i></span>
      {% endif %}
    </li>

    {% if forloop.last %}</ul>{% endif %}
  {% endfor %}
</div>
> I will keep updating this timeline whenever I read more manga.
{: .prompt-info }