---
title: Manga Reading Timeline
description: "Unveiling my manga journey: thoughts and timeline"
categories: [Animanga]
tags: [animanga, manga, timeline, books]
date: 2023-12-14 07:59:05 +05:30
---
> I suggest reading [my anime timeline]({% post_url 2023-12-14-anime-timeline %}) before this blog. There's no need to go over the specifics again.
{: .prompt-tip }

## Motivation
I don't classify myself as an avid manga reader, my usual go-to is checking out the manga versions of ongoing anime that leave me itching to know what happens next.

## Personal Insights
Like before, you can hover/click on the comments icon to uncover my thoughts (mostly spoiler-free) on each manga.

## Manga Grid
One last thing: Similar to my anime timeline, I have tried to make an image grid containing my favourite moments from manga as well. But, not every manga panel have similar dimensions. To smoothly automate the process, I have restricted myself to include only double-page spreads, which are typically more _spoilery_ than out-of-context anime screenshots. So, check out the grid at your own discretion :)
> And of course, the closer a manga is to the center, the closer it is to my heart ε>. Wait! Unlike anime, I haven't experienced as many manga, so it might not make much sense right now, but hopefully, one day it will ;)
{: .prompt-tip}

![Manga Grid](/manga-grid.jpg)
{% capture details_content %}
    <iframe src="{{ site.cdn }}/manga-grid.txt" width="100%"></iframe>
{% endcapture %}
{% include details-block-show.html
  id="captions"
    title="manga names"
    content=details_content
%}
If you are curious about how I created these high-resolution image grids, feel free to check out this [little repository]({{ site.url_prefixes.github.param }}/image-grid-generator).

## Timeline
Alright, let's dive right in!

{% include lang.html %}
{% include tooltip/style.html %}
{% assign df_strftime_m = site.data.locales[lang].df.archives.strftime | default: '/ %m' %}
{% assign df_dayjs_m = site.data.locales[lang].df.archives.dayjs | default: '/ MM' %}

<div class="pl-xl-3">
  {% for post in site.manga %}
    {% assign abbreviation = post.slug | slugify %}
    {% assign cur_year = post.date | date: '%Y' %}

    {% if cur_year != last_year %}
      {% unless forloop.first %}</ul>{% endunless %}

      <time id={{ cur_year }} class="year lead d-block">{{ cur_year }}</time>
      {{ '<ul class="list-unstyled">' }}

      {% assign last_year = cur_year %}
    {% endif %}

    <li id={{ abbreviation }} style="overflow-x: auto;  overflow-y: hidden; white-space: nowrap;">
      {% assign ts = post.date | date: '%s' %}
      <span class="date day" data-ts="{{ ts }}" data-df="DD">{{ post.date | date: '%d' }}</span>
      <span class="date month small text-muted ms-1" data-ts="{{ ts }}" data-df="{{ df_dayjs_m }}">
        {{ post.date | date: df_strftime_m }}
      </span>
      <a href="{{ site.url_prefixes.myanimelist.manga | append: "/" | append: post.code }}">{{ post.title }}</a>
      {% assign content = post.content | strip_newlines %}
      {% include tooltip/filter-animanga.html thoughts = post.content %}
      {% if content != "" %}
        <span data-bs-toggle="tooltip" data-bs-placement="top" data-bs-html="true" data-bs-trigger="hover focus" title = "{{ tooltip_title_animanga }}" ><i class="fa-fw fas fa-xs fa-comment"></i></span>
      {% endif %}
    </li>

    {% if forloop.last %}</ul>{% endif %}
  {% endfor %}
</div>
> I will keep updating this timeline whenever I read more manga.
{: .prompt-info }