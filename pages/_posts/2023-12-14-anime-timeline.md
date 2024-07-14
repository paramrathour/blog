---
title: Anime Watching Timeline
description: "Unveiling my anime journey: thoughts and timeline"
date: 2023-12-14 07:59:05 +05:30
categories: [Animanga, Timeline]
tags: [anime, timeline, thoughts]
---

## Motivation
While popular platforms like [Anilist](https://anilist.co/user/wrath3435/animelist) or [MyAnimeList](https://myanimelist.net/animelist/wrath3435) serve as valuable tools for anime tracking, they love to repeat stuff. There are seperate entries for each season, part, cour, movie, OVA, ... you name it.

I want to keep things simple -- one franchise, one entry.

## Personal Insights
I am no critic, but who doesn't like to share thoughts? To get a real deep dive into my experiences, I am sharing my two cents (mostly spoiler-free) on each anime.

Hover/Click on the comments icon to uncover these insights. Mobile users may need to rotate their device to landscape mode to read comments for longer titles.

These thoughts generally apply to the entirety of the anime, but in few cases, I have categorized my thoughts by seasons, especially where I felt a need due to varying opinions across each season.

## A Dilemma of Dates
Determining the timeline for this anime journey poses another challenge -- dates to assign. The date of completion seems like a suitable candidate. But anime suffers from a problem, most of them are not completed. For such uncompleted anime, a new season might be airing right now or it might be scheduled for later or it might never come. So, when do I actually 'complete' an anime? 

### Solution
Choose those dates when
- I have finished watching a completed anime or
- I am caught up with all existing material, with no new material airing at the time or
- I have seen everything that I wanted to see ( ͡ ° ͜ʖ ͡ °)

### The Forgotten Past
Back in 2018, I didn't use to track these dates. Also while creating this timeline, I realised I have lost some random dates. To handle such cases, I have chosen the last day of the month I likely 'completed' the show.

## Timeline
I probably overdid my explanations. Anyway, with no further ado, here's the timeline!

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
  {% for post in site.anime %}
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
      <a href="{{ 'https://myanimelist.net/anime/' | append: post.code }}">{{ post.title }}</a>
      {% assign content = post.content | strip_newlines %}
      {% if content != "" %}
        <span data-bs-toggle="tooltip" data-bs-placement="top" data-bs-html="true" data-bs-trigger="hover focus" title = "{{ post.content }}"><i class="fa-fw fas fa-xs fa-comment"></i></span>
      {% endif %}
    </li>

    {% if forloop.last %}</ul>{% endif %}
  {% endfor %}
</div>
> I will keep updating this timeline whenever I watch more anime.
{: .prompt-info }