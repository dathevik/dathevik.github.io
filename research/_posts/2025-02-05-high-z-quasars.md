---
layout: plain
title: High-redshift quasars
permalink: /research/high-redshift-quasars/
redirect_from:
  - /science/high-z-quasars/
  - /research/high-z-quasars/
sitemap: false
hide_last_modified: true
no_groups: true
---

Quasars at z &gt; 4.5 are our closest look at the first billion years of the universe. They tell us how supermassive black holes grew so large so early, what the galaxies around them were made of, and when the intergalactic gas was reionized. The problem is finding them: they are rare, and at these distances they look almost identical to the far more numerous cool stars in our own galaxy. Spectroscopy is the only certain confirmation, but it is far too expensive to run on every candidate, so the work begins with photometry and careful selection.

Three projects make up this line of work.

<!-- Each card is one link: the whole tile opens its project page, so there is no
     "read more". `project-status` is the short state of play, kept current by
     hand. See `.project-grid` in the styles below. -->

<div class="project-grid">
  <a class="project-card" href="/research/high-redshift-quasars/sed-selection/">
    <div class="project-thumb">
      <img src="/research/4most.jpg" alt="A deep field crowded with distant galaxies">
    </div>
    <div class="project-body">
      <span class="project-status">Published</span>
      <h2>Selecting quasars with SED fitting for 4MOST ChANGES</h2>
      <p>An SED fitting code I developed picks out candidates at 4.5 &lt; z &lt; 7 from large photometric surveys, in the southernmost sky where almost nothing had been searched before. The result is a catalog of around 6,000 candidates.</p>
    </div>
  </a>

  <a class="project-card" href="/research/high-redshift-quasars/radio-loud/">
    <!-- Cropped like the others despite being only 250px square: at this band
         height the crop scales it DOWN, so it stays sharp. Raising
         `.project-thumb` height much above 8rem would start to blow it up. -->
    <div class="project-thumb">
      <img src="/research/rl_qso.jpg" alt="Jet emerging from a radio-loud quasar">
    </div>
    <div class="project-body">
      <span class="project-status">In progress</span>
      <h2>Radio-loud quasars at z &gt; 5</h2>
      <p>Follow-up at Palomar and Gemini North confirmed three radio-loud quasars at z &gt; 5, the jetted sources hardest to explain this early. Radio, infrared and optical data are fitted together to rank what to observe next.</p>
    </div>
  </a>

  <a class="project-card" href="/research/high-redshift-quasars/lsst/">
    <div class="project-thumb">
      <img src="/research/surveys.webp" alt="The LSST camera at the Vera C. Rubin Observatory">
    </div>
    <div class="project-body">
      <span class="project-status">In progress</span>
      <h2>Simulating a dataset of AGN with LSST</h2>
      <p>Rubin, Euclid and Roman will image the sky deeper and wider than anything before, but only if photometric redshift methods keep up. I am building a mock catalog of AGN at LSST depth to test them.</p>
    </div>
  </a>
</div>

<p class="back"><a href="/research/">Back to Research</a></p>

<style>
  /* Projects sit side by side on one line, and fall to two then one column as
     the screen narrows. `auto-fit` + `minmax` does that without breakpoints:
     a card never gets narrower than 15rem, and leftover space is shared out. */
  .project-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(15rem, 1fr));
    gap: 1rem;
    margin: 0 0 1rem;
  }

  /* The whole tile is the link, so it needs the theme's link underline and
     colour stripped back off. `overflow: hidden` keeps the picture inside the
     rounded top corners. */
  .project-card {
    display: flex;
    flex-direction: column;
    overflow: hidden;
    border: 1px solid rgba(128, 128, 128, 0.35);
    border-radius: 6px;
    color: inherit;
    text-decoration: none;
    border-bottom: 1px solid rgba(128, 128, 128, 0.35);
    transition: border-color 200ms ease, transform 200ms ease, box-shadow 200ms ease;
  }

  .project-card:hover,
  .project-card:focus-visible {
    border-color: #36a9e1;
    transform: translateY(-2px);
    box-shadow: 0 4px 14px rgba(0, 0, 0, 0.12);
  }

  /* A shallow band, so the picture sets the tone without crowding out the text.
     Every thumbnail is cropped to this one box with `cover`, which is what keeps
     the three looking like a set: the source images have very different shapes,
     and fitting them instead would leave each sitting at its own apparent size.
     The band is deliberately short, because a wide image like the Rubin camera
     only crops (and so only zooms in) once the box is wider than it is. */
  .project-thumb {
    height: 7.5rem;
    flex: none;
    overflow: hidden;
  }

  .project-thumb img {
    display: block;
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 300ms ease;
  }

  .project-card:hover .project-thumb img {
    transform: scale(1.04);
  }

  .project-body {
    display: flex;
    flex-direction: column;
    padding: 1rem;
  }

  .project-status {
    align-self: flex-start;
    margin-bottom: 0.5rem;
    padding: 0.15rem 0.55rem;
    border-radius: 999px;
    background: rgba(54, 169, 225, 0.15);
    color: #36a9e1;
    font-size: 0.75em;
    font-weight: bold;
    letter-spacing: 0.02em;
    text-transform: uppercase;
  }

  .project-card h2 {
    margin: 0 0 0.4rem;
    font-size: 1.1em;
    line-height: 1.3;
  }

  .project-card p {
    margin: 0;
    font-size: 0.92em;
    line-height: 1.45;
  }

  .back a {
    color: #36a9e1;
    font-weight: bold;
    text-decoration: underline;
    text-decoration-thickness: 2px;
    text-underline-offset: 3px;
  }

  .back a:hover {
    filter: brightness(1.2);
  }

  .back {
    margin-top: 2rem;
  }
</style>
