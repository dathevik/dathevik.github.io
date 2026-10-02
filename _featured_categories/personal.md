---
layout: plain
title: Personal
permalink: /personal/
slug: personal
no_groups: true
sitemap: false
# Named by subject rather than image1..image7, so each one is obvious at a
# glance and stays matched to the paragraph it sits under in the page below.
image_hiking: /personal/hiking.jpeg
caption_hiking: "Patagonia W trek, pretty proud face"
image_paragliding: /personal/adventures.jpeg
caption_paragliding: "Trying paragliding the first time"
image_gothic: /personal/gothic.jpeg
caption_gothic: "At a Lacrimosa concert"
image_singing: /personal/singing.jpg
caption_singing: "Me in Khazers concert"
image_dnd: /personal/dnd.jpeg
caption_dnd: "Playing Dungeons and Dragons"
image_boardgames: /personal/bg.jpeg
caption_boardgames: "Twilight Imperium, one of the most epic board games I have played"
image_cooking: /personal/cook_book.jpeg
caption_cooking: "Swiss cooking workshop"
---

<p class="intro">A bit about me beyond the science nerdy stuff: what I am passionate about and what I like doing.</p>

<p class="news-note">
  If you want to keep track of my achievements, I log them on my <a href="/personal/news/"><strong>News</strong></a> page.
</p>

<!-- Each topic is a paragraph followed by its own photos, rather than all the
     text first and all the pictures after, so a photo sits with what it is
     about. The same text-then-picture rhythm as the Research and Teaching
     pages. Keep a new topic's photo row directly under its paragraph. -->

<div class="loves">
  <p class="lead-in">Now, about what I love.</p>

  <p>I love hiking and exploring nature, barefoot whenever possible. And I love adventures. Well, sometimes I do.</p>

  <div class="photo-row photo-row--portrait">
    <figure>
      <img src="{{ page.image_hiking }}" alt="Hiking in Patagonia">
      <figcaption>{{ page.caption_hiking }}</figcaption>
    </figure>
    <figure>
      <img src="{{ page.image_paragliding }}" alt="Paragliding for the first time">
      <figcaption>{{ page.caption_paragliding }}</figcaption>
    </figure>
  </div>

  <p>Gothic aesthetics and metal music have been part of me for over 12 years, so I guess this one is serious. I sing too. I started in a choir, and now I make covers, learn music production and DJ. Curious? Check out my <a href="https://soundcloud.com/dtatevik" target="_blank">SoundCloud</a> or listen to one of our choir concerts <a href="https://youtu.be/1UBZtaZ-yWg?si=gS3l_ohPyC_HchIt" target="_blank">here</a>.</p>

  <div class="photo-row photo-row--portrait">
    <figure>
      <img src="{{ page.image_gothic }}" alt="At a Lacrimosa concert">
      <figcaption>{{ page.caption_gothic }}</figcaption>
    </figure>
    <figure>
      <img src="{{ page.image_singing }}" alt="Singing at a Khazers concert">
      <figcaption>{{ page.caption_singing }}</figcaption>
    </figure>
  </div>

  <p>Board games? Absolutely. Mostly Euro games, but also DnD. I am always the one pushing to play something.</p>

  <div class="photo-row photo-row--landscape">
    <figure>
      <img src="{{ page.image_dnd }}" alt="Playing Dungeons and Dragons">
      <figcaption>{{ page.caption_dnd }}</figcaption>
    </figure>
    <figure>
      <img src="{{ page.image_boardgames }}" alt="Playing Twilight Imperium">
      <figcaption>{{ page.caption_boardgames }}</figcaption>
    </figure>
  </div>

  <p>I also organize cooking workshops with friends, each session dedicated to a different country's cuisine. So far: Armenia, Slovakia, Brazil, India, Chile, the UK and the US, with many more to come. I collect the recipes and stories into a cookbook of my own, which you can check out <a href="https://canva.link/8d5nhs9t9ccwjdj" target="_blank">here</a>.</p>

  <div class="photo-row photo-row--single">
    <figure>
      <img src="{{ page.image_cooking }}" alt="Swiss cooking workshop">
      <figcaption>{{ page.caption_cooking }}</figcaption>
    </figure>
  </div>
</div>

<style>
  .intro {
    margin: 0 0 0.5rem;
  }

  .news-note {
    margin: 0 0 1.25rem;
    font-size: 0.95em;
  }

  .lead-in {
    font-weight: bold;
  }

  .news-note a,
  .loves a {
    color: #36a9e1;
    font-weight: bold;
    text-decoration: underline;
    text-decoration-thickness: 2px;
    text-underline-offset: 3px;
  }

  .news-note a:hover,
  .loves a:hover {
    filter: brightness(1.2);
  }

  .loves p {
    margin: 0 0 0.4rem;
    line-height: 1.45;
  }

  /* Breathing room where a photo row sits between two paragraphs. */
  .loves .photo-row {
    margin-top: 0.9rem;
    margin-bottom: 1.6rem;
  }

  .loves {
    margin-bottom: 1.5rem;
  }

  .photo-row {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: flex-start;
    gap: 1rem;
    margin-bottom: 1.25rem;
  }

  .photo-row figure {
    margin: 0;
    flex: 1 1 15rem;
    max-width: 22rem;
  }

  /* Matches the combined width of a two-photo row: 22rem + 1rem gap + 22rem */
  .photo-row--single figure {
    flex: 0 1 45rem;
    max-width: 45rem;
  }

  /* Photos in a row share one aspect ratio so they end up exactly the same
     height. Without this they kept their own proportions, and a slightly
     squarer picture (singing.jpg is 772x960, against 1204x1600 beside it) came
     out visibly shorter than its neighbour.

     The ratio is set per row to match the pictures actually in it, so the crop
     stays almost nothing: the portraits are already close to 3:4 and the
     landscapes are exactly 4:3. Picking one ratio for the whole page would have
     meant cutting the portraits in half. Put a new row in whichever class fits
     its photos, and crop with `cover` so nothing is ever stretched. */
  .photo-row img {
    display: block;
    width: 100%;
    height: auto;
    object-fit: cover;
    border-radius: 4px;
  }

  .photo-row--portrait img {
    aspect-ratio: 3 / 4;
    height: auto;
  }

  .photo-row--landscape img,
  .photo-row--single img {
    aspect-ratio: 4 / 3;
    height: auto;
  }

  .photo-row figcaption {
    margin-top: 0.3rem;
    text-align: center;
    font-style: italic;
    font-size: 0.8em;
    line-height: 1.3;
  }
</style>
