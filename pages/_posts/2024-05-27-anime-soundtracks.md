---
layout: post
title: Celebrating 25 Years of Anime Soundtracks
description: "Looking back on awesome composers and their amazing music"
categories: [Animanga]
tags: [anime, music]
toc: false
date: 2024-05-27 20:51 +0530
---
## Introduction
Anime soundtracks holds a special place in my heart. A _soundtrack_ (aka OST) for me is a fancy term for denoting background music. Though in principle, a soundtrack is much more than that and includes all the audio elements and not just the music.
You may refer to my OST playlist [paramrathour.github.io/anime-osts](https://paramrathour.github.io/anime-osts), to get an idea of the concept.

Now, I recently made this <a href="https://docs.google.com/presentation/d/1_kR1Gy2ggiaWxK3tw-FMauAW1uJaz6yyYHpFhBzSYvc">anime OST quiz</a>. Its objective was the guess the anime and the composer by listening to the OSTs of some anime. The quiz contained OSTs of anime from the last two decades (2001-2010, 2011-2020). In total, there were 20 anime from unique years and composed by unique composer. It was my first time hosting an anime-related quiz, but it turned out to be quite fun. As I had already done my research for the quiz, I thought to expand upon it in this blog post.

As a result, this blog will cover anime OSTs from the first quarter of 21st century (2001-2025)[^rip2025] -- one per year, per composer, per franchise.

### A Dillemma of Years
A problem similar to the one discussed in [my anime timeline]({% post_url 2023-12-14-anime-timeline %}) arises. Usually anime can go on longer than a year, can be broken up into cours/seasons over multiple years or it can just stop.
This gives rise to a problem of determining the _year_ an OST belongs to -- maybe the ideal solution is to pinpoint the exact day of the episode containing the OST was publicly released, but this is a time-consuming process. Instead, I have taken the answer as the starting year of the season/cour featuring the given OST.

### Hold on
Let's make some important announcements to ease your navigation.
- Some creators don't allow embedded YouTube video playback on external sites. If such cases, you can either click on video links to open it within the YouTube interface or you can simply refer to this <a href="https://youtube.com/playlist?list=PLaO_HkPtJoP0pM9ZfMenDhoOGun_ilLA9">playlist</a> containing the OST from each year.
- While providing my insights on each composer, I have added many other youtube videos as a plain hyperlink. Such videos are also available <a href="https://youtube.com/playlist?list=PLaO_HkPtJoP1fdEAxZxd5VczOJLzRjc0C">here</a> in the order they are mentioned in this post.

> The media attached on this page belongs to their respective owners. Also, I have tried my best include official release videos.
{: .prompt-info}
<!-- ## 2000s -->
<div id="post-list" class="pl-xl-3">
{% for post in site.music %}
	{% if post.category == "OST" %}
		<h2>{{ post.year }}</h2>
		{% include embed/youtube.html id=post.video_id %}	
		<dl>
			<dt>Anime Name</dt>
				<dd><a href="{{ 'https://myanimelist.net/anime/' | append: post.anime_code }}">{{ post.anime }}</a></dd>
			<dt>Composer Name</dt>
				<dd><a href="{{ 'https://myanimelist.net/people/' | append: post.composer_code }}">{{ post.composer }}</a></dd>
		</dl>
		{{ post.content }}
	{% endif %}
{% endfor %}
</div>

## Wrap Up
And that's it for now. Thanks for reading a (possibly) useless blog post as music is entirely subjective.

## Footnotes
[^rip2025]: 2025 isn't here yet, hopefully I will remember to update this blog post.