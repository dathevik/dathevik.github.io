---
layout: plain
title: Science
permalink: /science/
slug: science
no_groups: true
sitemap: false
gif_highz: /science/sr2f57539f4ba17-ezgif.com-speed.gif
caption_highz: "Searching for quasars in the early universe"
anim_cgm: /science/pso352_lya_halo.webp
caption_cgm: "Lyman alpha emission around the radio-loud quasar PSO J352-15"
---

<p class="intro">Quasars are the most luminous Active Galactic Nuclei, powered by accretion onto the supermassive black holes at the centers of their galaxies. They outshine everything around them, they emit across the whole electromagnetic spectrum, and each wavelength range tells us about a different part of the system: the relativistic jet, the dusty torus, the accretion disk, the corona, and the gas surrounding it. They also shape the galaxies they live in, injecting energy through jets, winds and radiation that can either shut down star formation or trigger it. I study quasars at the earliest cosmic times, when the universe was less than a billion years old.</p>

<p class="lead-in">My research interests are the following.</p>

<section class="project">
  <figure class="project-media break-layout">
    <div class="media-frame">
      <img src="{{ page.gif_highz }}" alt="Searching for high-redshift quasars">
      <span class="media-title">High redshift quasars</span>
    </div>
    <figcaption>{{ page.caption_highz }}</figcaption>
  </figure>
  <h2>Finding the highest redshift quasars</h2>
  <p>I look for quasars at 4.5 &lt; z &lt; 7, reaching back to the very beginning of the universe, using an SED fitting code I developed. So far this has produced a catalog of around 6,000 candidates that are now being observed spectroscopically. Among them I hunt for the most extreme sources, the jetted quasars that stay enormously powerful even at these redshifts, and I work on the methods that will let the next generation of imaging surveys find many more.</p>
  <p class="learn-more"><a href="/science/high-z-quasars/">Learn more about it</a></p>
</section>

<section class="project">
  <figure class="project-media break-layout">
    <div class="media-frame media-frame--contain">
      <img src="{{ page.anim_cgm }}" alt="Lyman alpha halo around a high-redshift radio-loud quasar">
      <span class="media-title">The galaxy fuel in the very early universe: Circumgalactic medium</span>
    </div>
    <figcaption>{{ page.caption_cgm }}</figcaption>
  </figure>
  <h2>The gas that feeds early galaxies</h2>
  <p>Quasars in the early universe sit in massive galaxies fed by enormous reservoirs of cool gas, the circumgalactic medium. This gas is the fuel for star formation and it regulates how galaxies grow. I map it through its Lyman alpha emission with VLT/MUSE around radio-loud quasars at 3.6 &lt; z &lt; 6.2, to find out how the powerful jets interact with the material that feeds their galaxies.</p>
  <p class="learn-more"><a href="/science/cgm/">Learn more about it</a></p>
</section>

<p class="lead-in more-sections">More on my work.</p>

<p class="section-links">
  <a href="/science/publications/"><strong>Publications</strong></a><br>
  <a href="/science/talks/"><strong>Talks &amp; Presentations</strong></a><br>
  <a href="/science/collaborations/"><strong>Collaborations</strong></a><br>
  <a href="/science/outreach/"><strong>Outreach</strong></a>
</p>

<style>
  .intro {
    margin: 0 0 1rem;
    line-height: 1.45;
  }

  .lead-in {
    font-weight: bold;
    margin: 0 0 1.25rem;
  }

  .more-sections {
    margin-top: 2rem;
  }

  .project {
    margin-bottom: 2.25rem;
  }

  .project-media {
    margin: 0 0 0.6rem;
  }

  /* Wide band that runs to the edge of the page. The theme's `break-layout`
     class handles the width; this sets the landscape proportions. */
  .media-frame {
    position: relative;
    height: 20rem;
    overflow: hidden;
    border-radius: 4px;
  }

  .media-frame img {
    display: block;
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  /* The Lya animation has a transparent background, so it is fitted rather
     than cropped and the page shows through around it. */
  .media-frame--contain img {
    object-fit: contain;
  }

  .media-title {
    position: absolute;
    left: 0;
    bottom: 0;
    max-width: 100%;
    padding: 0.6rem 1rem;
    background: rgba(25, 55, 71, 0.6);
    color: #fff;
    font-weight: bold;
    font-size: 1.35em;
    line-height: 1.25;
    border-radius: 0 4px 0 4px;
  }

  .project h2 {
    margin: 0 0 0.4rem;
    font-size: 1.25em;
  }

  .project p {
    margin: 0 0 0.4rem;
    line-height: 1.45;
  }

  .learn-more {
    margin-bottom: 0;
  }

  .learn-more a,
  .section-links a {
    color: #36a9e1;
    font-weight: bold;
    text-decoration: underline;
    text-decoration-thickness: 2px;
    text-underline-offset: 3px;
  }

  .learn-more a:hover,
  .section-links a:hover {
    filter: brightness(1.2);
  }

  .section-links {
    font-size: 1.2em;
    line-height: 1.9;
  }

  @media (max-width: 40rem) {
    .media-frame {
      height: 13rem;
    }

    .media-title {
      font-size: 1.05em;
      padding: 0.45rem 0.7rem;
    }
  }
</style>
