---
layout: plain
title: About me
sitemap: false
permalink: /
hide_last_modified: true
no_grouping: true
---

Welcome to my room! I’m an Armenian astrophysicist based in Santiago, Chile, currently pursuing a PhD at the Instituto de Estudios Astrofísicos, Universidad Diego Portales. I study high-redshift quasars and their environments, exploring how these distant supermassive black holes shape the galaxies around them.

Beyond astrophysics, I have 5+ years of experience in education as a certified physics content creator and methodological trainer for Armenia’s Ministry of Education. I’ll be sharing some of my approaches to learning, research, and surviving academic chaos here, so don’t wander too far! Outside science, I’m also interested in philosophy, particularly the philosophy of education and science. After my PhD, I plan to stay on the dark side of academia. While some dream of early retirement, I dream of becoming a professor, sharing science with curious minds, and convincing the already retired to fund us a little longer, so we can keep investigating the universe’s most mysterious black creatures.

To learn more about my work and me, feel free to explore the rest of my website!

<!-- Two current pieces of work, each one link covering the picture and the
     text. Keep this to two: it is a taster for the Research section, not a
     list of everything. -->

<h2 class="latest-title">Latest work</h2>

<div class="latest">
  <a class="latest-item" href="/research/circumgalactic-medium/lya-halos/">
    <span class="latest-thumb latest-thumb--contain">
      <img src="/research/pso352_lya_halo.webp" alt="Lyman alpha halo around the quasar PSO J352-15">
    </span>
    <span class="latest-text">
      <strong>Lyman alpha halos around radio-loud quasars</strong>
      <span>Mapping the cool gas feeding galaxies in the early universe with VLT/MUSE.</span>
    </span>
  </a>

  <a class="latest-item" href="/research/high-redshift-quasars/radio-loud/">
    <span class="latest-thumb">
      <img src="/research/rl_qso.jpg" alt="Jet emerging from a radio-loud quasar">
    </span>
    <span class="latest-text">
      <strong>Searching for radio-loud quasars at z &gt; 5</strong>
      <span>Finding and characterizing the most extreme jetted quasars in the early universe.</span>
    </span>
  </a>
</div>

<p style="font-size: 0.85em; font-style: italic; color: #888; margin-top: 2rem;">
  Sidebar photo by <strong>k3stalker</strong>.
</p>

<style>
  .latest-title {
    margin: 2rem 0 0.75rem;
    font-size: 1.15em;
  }

  .latest {
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
  }

  /* A wide, shallow bar: picture on the left, text on the right. The whole bar
     is the link, so the theme's underline and link colour are stripped off. */
  .latest-item {
    display: flex;
    align-items: center;
    gap: 1.1rem;
    padding: 1rem 1.1rem;
    border: 1px solid rgba(128, 128, 128, 0.35);
    border-radius: 6px;
    color: inherit;
    text-decoration: none;
    border-bottom: 1px solid rgba(128, 128, 128, 0.35);
    transition: border-color 200ms ease, transform 200ms ease, box-shadow 200ms ease;
  }

  .latest-item:hover,
  .latest-item:focus-visible {
    border-color: #36a9e1;
    transform: translateY(-2px);
    box-shadow: 0 4px 14px rgba(0, 0, 0, 0.12);
  }

  .latest-thumb {
    flex: none;
    width: 7.5rem;
    height: 7.5rem;
    overflow: hidden;
    border-radius: 4px;
    background: #05060a;
  }

  .latest-thumb img {
    display: block;
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  /* The Lyman alpha animation has a transparent background and would lose the
     halo if cropped square, so it is fitted on the dark backdrop instead. */
  .latest-thumb--contain img {
    object-fit: contain;
  }

  .latest-text {
    display: flex;
    flex-direction: column;
    gap: 0.15rem;
    min-width: 0;
  }

  .latest-text strong {
    font-size: 1.1em;
    line-height: 1.3;
  }

  .latest-text > span {
    font-size: 0.95em;
    line-height: 1.45;
    opacity: 0.8;
  }

  @media (max-width: 30rem) {
    .latest-thumb {
      width: 5rem;
      height: 5rem;
    }
  }
</style>
