---
title: Book Reading Timeline
description: "Unveiling my book journey: thoughts and timeline"
categories: [Books]
tags: [books, timeline]
date: 2025-03-02 19:59 +0530
---
## Motivation
After [anime]({% post_url 2023-12-14-anime-timeline %}) and [manga]({% post_url 2023-12-14-manga-timeline %}), I am back with another timeline as I have finally restarted reading books outside of math and manga sphere. 
Even though I recently created a [goodreads](https://www.goodreads.com/wrath3435) account, it has simply too much clutter and unnecessary stuff. Like having separate entries for every books of the same series and the obsession with ratings. Here, I keep things minimalistic.

## More Repetitive Stuff
Before you dive in, here are a few things to know. Since it's mostly repetitive, I won't go over it all again here. Check out [the other timeline]({% post_url 2023-12-14-anime-timeline %}) for more details!

Omissions from the Collection
: Not all the books I read will be on here. I maintain a [manga timeline]({% post_url 2023-12-14-manga-timeline %}) for Japanese graphic novels already, and, I don't think people _really_ want to know about my academic textbooks with raw math. So, I am leaving out anything that's not oriented towards general audience, I would love to share them but somewhere not here :)

Personal Insights
: Just like my other timelines, I will share my two cents (mostly spoiler-free) on each read.\
Hover/Click on the comments icon to uncover these insights.

The Forgotten Past
: Until recently, I didn't use to track completion dates. To handle cases where I don't remember the dates, I have chosen the last day (month) of the forgotten month (year).

Series Struggles
: In case of a book series, my thoughts generally apply to its entirety, but in some cases, I might need to categorize my thoughts by individual books, especially where I felt a need due to varying opinions across each book.\
Another issue comes up while deciding the date of completion, let's just say that is up to me ( ͡ ° ͜ʖ ͡ °)

## The Firsts
It's tough to pinpoint my first book, but it was probably a cricket book covering most matches from the 1975 to 2003 Cricket World Cups; I guess I have been a cricket fan for ages. Apart from that and the science encyclopedias, I remember reading a lot of fables and folklore like [Hitopadesha]({{ site.url_prefixes.wikipedia}}/Hitopadesha), [Panchatantra]({{ site.url_prefixes.wikipedia}}/Panchatantra), Tales of Akbar-Birbal as well stories from the epic of [Mahabharata]({{ site.url_prefixes.wikipedia}}/Mahabharata) and [Ramayana]({{ site.url_prefixes.wikipedia}}/Ramayana). But I decided against including such books because they weren't the "definitive" version written in the original language, and, I don't remember them that well anyway.

## Timeline

{% include lang.html %}
{% include tooltip/style.html %}
{% assign df_strftime_m = site.data.locales[lang].df.archives.strftime | default: '/ %m' %}
{% assign df_dayjs_m = site.data.locales[lang].df.archives.dayjs | default: '/ MM' %}

<div class="pl-xl-3">
  {% for post in site.books %}
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
      {% if post.code != nil1 %}
        <a href="{{ site.url_prefixes.goodreads.book | append: "/" | append: post.code }}">{{ post.title }}</a>
      {% elsif post.series != nill %}
        <a href="{{ site.url_prefixes.goodreads.series | append: "/" | append: post.series }}">{{ post.title }}</a>
      {% else %}
        <a href="{% post_url 2025-03-02-book-timeline %}">{{ post.title }}</a>
      {% endif %}
      {% assign content = post.content | strip_newlines %}
      {% include tooltip/filter-animanga.html thoughts = post.content %}
      {% if content != "" %}
        <span data-bs-toggle="tooltip" data-bs-placement="top" data-bs-html="true" data-bs-trigger="hover focus" title = "{{ tooltip_title_animanga }}" ><i class="fa-fw fas fa-xs fa-comment"></i></span>
      {% endif %}
    </li>

    {% if forloop.last %}</ul>{% endif %}
  {% endfor %}
</div>
> I will keep updating this timeline whenever I read more books.
{: .prompt-info }
