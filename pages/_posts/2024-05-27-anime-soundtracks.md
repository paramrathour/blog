---
title: Celebrating 25 Years of Anime Soundtracks
description: "Looking back on awesome composers and their amazing music"
categories: [Animanga]
tags: [animanga, anime, music, timeline, featured-content]
date: 2024-05-27 20:51 +0530
---
## Introduction
Soundtracks have always held a special place in my heart. Since school days, I have gravitated more towards music than songs, whether it was the _epic_ music by [small]({{ site.url_prefixes.youtube.video }}/v9H8PBUf_bI) [independent]({{ site.url_prefixes.youtube.video }}/DKslLkxroSE) [composers]({{ site.url_prefixes.youtube.video }}/6S8FXwY7wjs), the score of a [sc]({{ site.url_prefixes.youtube.video }}/GwzmCS-Eczo)[i]({{ site.url_prefixes.youtube.video }}/dBVFQB0-Q1E)[e]({{ site.url_prefixes.youtube.video }}/nBpOmaBwIYg)[n]({{ site.url_prefixes.youtube.video }}/Gs_LcX_M0Dk)[ce]({{ site.url_prefixes.youtube.video }}/h3sg_lOF7KI) show, the themes from [cricket]({{ site.url_prefixes.youtube.video }}/Nd-DlMOLCY4) [events]({{ site.url_prefixes.youtube.video }}/--ugmI8F2vg), [ads]({{ site.url_prefixes.youtube.video }}/0OiJvgjwL9U), [m]({{ site.url_prefixes.youtube.video }}/EJrkP6zf09g)[o]({{ site.url_prefixes.youtube.video }}/KxoaCW8EEDE)[v]({{ site.url_prefixes.youtube.video }}/C_yKDS0I9Xs)[i]({{ site.url_prefixes.youtube.video }}/DTcc0xWBbEU)[e]({{ site.url_prefixes.youtube.video }}/y4nFE8QAZM0)[s]({{ site.url_prefixes.youtube.video }}/1iFqID2vg28), [Indian]({{ site.url_prefixes.youtube.video }}/x78zAfwDv9c) [T]({{ site.url_prefixes.youtube.video }}/gWV9U8Sik3U)[V]({{ site.url_prefixes.youtube.video }}/sQrd3W3QXS8) [serials]({{ site.url_prefixes.youtube.video }}/QhAaSVgEPlg), or even [edutainment]({{ site.url_prefixes.youtube.video }}/GMMWQXk6deY) [YouTube]({{ site.url_prefixes.youtube.video }}/2p8Rt82oubE) [videos]({{ site.url_prefixes.youtube.video }}/V0bxY-vPuYU).[^shoutouts] So, when I eventually got into anime, it was no surprise that its music immediately caught my attention. And then I realised something fascinating, it was highly likely that I will enjoy the anime if I loved its soundtrack.

Now, coming to the definition, a _soundtrack_ (aka OST) for me, is a fancy term for denoting background music. However, in principle, a soundtrack is much more than that; it includes all the audio elements and not just the music.
You may refer to my OST playlist, [paramrathour.github.io/anime-osts]({{ site.url }}/anime-osts), [paramrathour.github.io/cinematic-music]({{ site.url }}/cinematic-music), to get an idea of the concept. I also maintain an [interest stack]({{ site.url_prefixes.myanimelist.stacks }}/9687) for some of my favourite anime soundtracks.

## Motivation
I recently made this [anime OST quiz](https://docs.google.com/presentation/d/1_kR1Gy2ggiaWxK3tw-FMauAW1uJaz6yyYHpFhBzSYvc). Its objective was to guess the anime and the composer by listening to the OSTs of some anime. The quiz contained OSTs of anime from the last two decades (2001-2010, 2011-2020). In total, there were 20 anime from unique years and composed by unique composers. It was my first time hosting an anime-related quiz, but it turned out to be quite fun. As I had already done my research for the quiz, I thought I would expand upon it in this blog post. And, I have also added some _juicy_ tidbits that I mentioned during the quiz.

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

#### 2025
Coming soon (hopefully ;)

## Wrap Up
And that's it for now. Thanks for reading a (possibly) useless blog post, as music is entirely subjective.

### Footnotes
[^shoutouts]: I have simply mentioned from where I first heard the score. It is entirely possible that the piece was not composed specifically for that event but was instead reused -- similar to [Conquest of Paradise]({{ site.url_prefixes.youtube.video }}/Nd-DlMOLCY4), which is a popular standalone track composed by Vangelis but I first came across it during the 2011 Cricket World Cup, so I ended up associating it with _cricket_ events.
[^rip2025]: 2025 isn't here yet. Hopefully, I will remember to update this blog post.