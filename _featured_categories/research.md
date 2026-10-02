---
layout: plain
title: Research
permalink: /research/
redirect_from:
  - /science/
slug: research
no_groups: true
sitemap: false
gif_highz: /research/sr2f57539f4ba17-ezgif.com-speed.gif
caption_highz: "Searching for quasars in the early universe"
anim_cgm: /research/pso352_lya_halo.webp
caption_cgm: "Lyman alpha emission around the radio-loud quasar PSO J352-15. Visualization code by Dr. Emanuele Farina."
---

<!-- The long explainer about what quasars are used to open this page. It was
     removed because each research topic now explains itself on its own page,
     and repeating it here only delayed getting to them. -->

<p class="intro">My scientific interests include galaxy formation and evolution, AGN, observational astronomy, astronomical surveys, and data analysis. I also have a soft spot for theoretical physics, especially gravitational field theory. There’s something deeply romantic about it that keeps pulling me back.</p>

<p class="lead-in">More specific interests and projects.</p>

<!-- Each section is a banner photo that links to its subpage, with the subpage's
     own name laid over it, then a short description. The photo and the name on it
     are one link, so clicking anywhere on the image navigates there. -->

<section class="project">
  <figure class="project-media break-layout">
    <a class="media-link" href="/research/high-redshift-quasars/">
      <div class="media-frame">
        <img src="{{ page.gif_highz }}" alt="Searching for high-redshift quasars">
        <span class="media-title">High-redshift quasars</span>
      </div>
    </a>
    <figcaption>{{ page.caption_highz }}</figcaption>
  </figure>
  <p>I look for quasars at 4.5 &lt; z &lt; 7, reaching back to the very beginning of the universe, using an SED fitting code I developed. So far this has produced a catalog of around 6,000 candidates that are now being observed spectroscopically. Among them I hunt for the most extreme sources, the jetted quasars that stay enormously powerful even at these redshifts, and I work on the methods that will let the next generation of imaging surveys find many more.</p>
  <p class="learn-more"><a href="/research/high-redshift-quasars/">Learn more about it</a></p>
</section>

<section class="project">
  <figure class="project-media break-layout">
    <a class="media-link" href="/research/circumgalactic-medium/">
      <div class="media-frame media-frame--contain">
        <img src="{{ page.anim_cgm }}" alt="Lyman alpha halo around a high-redshift radio-loud quasar">
        <span class="media-title">Circumgalactic medium</span>
      </div>
    </a>
    <figcaption>{{ page.caption_cgm }}</figcaption>
  </figure>
  <p>Quasars in the early universe sit in massive galaxies fed by enormous reservoirs of cool gas, the circumgalactic medium. This gas is the fuel for star formation and it regulates how galaxies grow. I map it through its Lyman alpha emission with VLT/MUSE around radio-loud quasars at 3.66 &lt; z &lt; 6.44, to find out how the powerful jets interact with the material that feeds their galaxies.</p>
  <p class="learn-more"><a href="/research/circumgalactic-medium/">Learn more about it</a></p>
</section>

<p class="lead-in more-sections">More on my work.</p>

<p class="section-links">
  <a href="/research/publications/"><strong>Publications</strong></a><br>
  <a href="/research/talks/"><strong>Talks</strong></a><br>
  <a href="/research/collaborations/"><strong>Collaborations</strong></a><br>
  <a href="/research/outreach/"><strong>Outreach and press</strong></a>
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

  /* The banner is one link wrapping the image and its title. Strips the theme's
     link underline and colour, and adds a hover cue, since there is no longer a
     heading underneath to say the section is clickable. */
  .media-link {
    display: block;
    color: inherit;
    text-decoration: none;
    border-bottom: none;
  }

  .media-frame img,
  .media-title {
    transition: transform 300ms ease, background 200ms ease;
  }

  .media-link:hover .media-frame img {
    transform: scale(1.03);
  }

  .media-link:hover .media-title {
    background: rgba(25, 55, 71, 0.85);
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
