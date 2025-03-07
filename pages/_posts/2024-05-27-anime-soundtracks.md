---
title: Celebrating 25 Years of Anime Soundtracks
description: "Looking back on awesome composers and their amazing music"
categories: [Animanga]
tags: [animanga, anime, music, timeline, featured-content]
date: 2024-05-27 20:51 +0530
---
## Introduction
Anime soundtracks hold a special place in my heart. A _soundtrack_ (aka OST) for me, is a fancy term for denoting background music. However, in principle, a soundtrack is much more than that; it includes all the audio elements and not just the music.
You may refer to my OST playlist, [paramrathour.github.io/anime-osts]({{ site.url }}/anime-osts), to get an idea of the concept. I also maintain an [interest stack]({{ site.url_prefixes.myanimelist.stacks }}/9687) for some of my favourite anime soundtracks.

I recently made this [anime OST quiz](https://docs.google.com/presentation/d/1_kR1Gy2ggiaWxK3tw-FMauAW1uJaz6yyYHpFhBzSYvc). Its objective was to guess the anime and the composer by listening to the OSTs of some anime. The quiz contained OSTs of anime from the last two decades (2001-2010, 2011-2020). In total, there were 20 anime from unique years and composed by unique composers. It was my first time hosting an anime-related quiz, but it turned out to be quite fun. As I had already done my research for the quiz, I thought I would expand upon it in this blog post. I have also added some _juicy_ tidbits that I mentioned during the quiz.

As a result, this blog will cover anime OSTs from the first quarter of the 21st century (2001-2025)[^rip2025] -- **one per year, per composer, per franchise**.

## A Dilemma of Years
A problem similar to the one discussed in [my anime timeline]({% post_url 2023-12-14-anime-timeline %}) arises. Usually, anime can go on longer than a year, can be broken up into cours/seasons over multiple years, or it can just stop.
This gives rise to the problem of determining the _year_ an OST belongs to -- maybe the ideal solution is to pinpoint the exact day the episode containing the OST was publicly released, but this is a time-consuming process. Instead, I have taken the answer as the starting year of the season/cour featuring the given OST.

### Hold on
Let's make some important announcements to ease your navigation.
- Creators can block embedded YouTube video playback on external sites. To accommodate for such cases, you can either click on video links to open it within the YouTube interface or simply refer to this [playlist]({{ site.url_prefixes.youtube.playlist }}PLaO_HkPtJoP0pM9ZfMenDhoOGun_ilLA9) containing the OST from each year.
- While providing my insights on each composer, I have added many other YouTube videos as a plain hyperlink. I have added such videos to this [playlist]({{ site.url_prefixes.youtube.playlist }}PLaO_HkPtJoP1fdEAxZxd5VczOJLzRjc0C) in the order they are mentioned in this post.

> The media attached on this page belongs to their respective owners. I have tried my best to include official releases but only some tracks are available in my country.
{: .prompt-info}
## Timeline
<div id="post-list" class="pl-xl-3">
{% for post in site.music %}
	{% if post.category == "OST" %}
		{% assign abbreviation = post.slug | slugify %}
		{% assign current_year = post.year %}
		{% assign current_decade = current_year | divided_by: 10 | times: 10 %}
		{% if current_decade != last_decade %}
			<h3 id="{{ current_decade }}s" >{{ current_decade }}s</h3>
			{% assign last_decade = current_decade %}
		{% endif %}
		<h4 id="{{ abbreviation }}" >{{ current_year }}</h4>
		{% include embed/youtube.html id=post.video_id %}
		<dl>
			<dt>Anime Name</dt>
				<dd><a href="{{ site.url_prefixes.myanimelist.anime | append: '/' | append: post.anime_code }}">{{ post.title }}</a></dd>
			<dt>Composer Name</dt>
				<dd><a href="{{ site.url_prefixes.myanimelist.people | append: '/' | append: post.composer_code }}">{{ post.composer }}</a></dd>
		</dl>
		{{ post.content | flatify | markdownify}}
	{% endif %}
{% endfor %}
</div>

## Wrap Up
And that's it for now. Thanks for reading a (possibly) useless blog post, as music is entirely subjective.

### Footnotes
[^rip2025]: 2025 isn't here yet. Hopefully, I will remember to update this blog post.