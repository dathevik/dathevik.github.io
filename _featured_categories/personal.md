---
layout: plain
title: Personal
permalink: /personal/
slug: personal
no_groups: true
sitemap: false
image1: /personal/hiking.jpeg
image_caption1: "Patagonia W trek, pretty proud face"
image2: /personal/adventures.jpeg
image_caption2: "Trying paragliding the first time"
image3: /personal/gothic.jpeg
image_caption3: "At a Lacrimosa concert"
image4: /personal/dnd.jpeg
image_caption4: "Playing Dungeons and Dragons"
image5: /personal/singing.jpg
image_caption5: "Me in Khazers concert"
image6: /personal/bg.jpeg
image_caption6: "Twilight Imperium, one of the most epic board games I have played"
image7: /personal/cook_book.jpeg
image_caption7: "Cover of my cookbook from the cooking workshops"
---

<p class="intro">A bit about me beyond the science nerdy stuff: what I am passionate about and what I like doing.</p>

<p class="news-note">
  If you want to keep track of my achievements, I log them on my <a href="/personal/news/"><strong>News</strong></a> page.
</p>

<div class="loves">
  <p class="lead-in">Now, about what I love.</p>

  <p>I love hiking and exploring nature, barefoot whenever possible. And I love adventures. Well, sometimes I do.</p>

  <p>Gothic aesthetics and metal music have been part of me for over 12 years, so I guess this one is serious. I sing too. I started in a choir, and now I make covers, learn music production and DJ. Curious? Check out my <a href="https://soundcloud.com/dtatevik" target="_blank">SoundCloud</a> or listen to one of our choir concerts <a href="https://youtu.be/1UBZtaZ-yWg?si=gS3l_ohPyC_HchIt" target="_blank">here</a>.</p>

  <p>Board games? Absolutely. Mostly Euro games, but also DnD. I am always the one pushing to play something.</p>

  <p>I also organize cooking workshops with friends, each session dedicated to a different country's cuisine. So far: Armenia, Slovakia, Brazil, India, Chile, the UK and the US, with many more to come. I collect the recipes and stories into a cookbook of my own, which you can check out <a href="https://canva.link/8d5nhs9t9ccwjdj" target="_blank">here</a>.</p>
</div>

<div class="photo-row">
  <figure>
    <img src="{{ page.image1 }}" alt="hiking">
    <figcaption>{{ page.image_caption1 }}</figcaption>
  </figure>
  <figure>
    <img src="{{ page.image2 }}" alt="paragliding">
    <figcaption>{{ page.image_caption2 }}</figcaption>
  </figure>
</div>

<div class="photo-row">
  <figure>
    <img src="{{ page.image3 }}" alt="gothic">
    <figcaption>{{ page.image_caption3 }}</figcaption>
  </figure>
  <figure>
    <img src="{{ page.image5 }}" alt="singing">
    <figcaption>{{ page.image_caption5 }}</figcaption>
  </figure>
</div>

<div class="photo-row">
  <figure>
    <img src="{{ page.image4 }}" alt="Dungeons and Dragons">
    <figcaption>{{ page.image_caption4 }}</figcaption>
  </figure>
  <figure>
    <img src="{{ page.image6 }}" alt="board games">
    <figcaption>{{ page.image_caption6 }}</figcaption>
  </figure>
</div>

<div class="photo-row photo-row--single">
  <figure>
    <img src="{{ page.image7 }}" alt="cookbook">
    <figcaption>{{ page.image_caption7 }}</figcaption>
  </figure>
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

  .photo-row img {
    display: block;
    width: 100%;
    height: auto;
    border-radius: 4px;
  }

  .photo-row figcaption {
    margin-top: 0.3rem;
    text-align: center;
    font-style: italic;
    font-size: 0.8em;
    line-height: 1.3;
  }
</style>
