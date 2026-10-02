---
layout: plain
title: "CV"
permalink: /cv/
# Shown under the intro below. Update this whenever the PDF is replaced.
# It is kept by hand on purpose: the file's own timestamp is reset by the
# checkout step on every CI build, so it would always read as the deploy date.
cv_updated: 2026-10-01
---

<!-- No "# CV" heading here: the page title above is already rendered as the
     page's H1, so a heading repeating it shows the word twice. -->

Here is a preview of my **CV** in PDF.

<!-- No download link here: the embedded PDF viewer has its own download
     button, so a second one is redundant. -->
<p class="cv-meta">Last updated {{ page.cv_updated | date: "%-d %B %Y" }}</p>

<iframe src="{{ '/cv/Tatevik_Mkrtchyan_CV.pdf' | relative_url }}" width="100%" height="750px">
  This browser does not support PDFs. Please download the PDF to view it: <a href="{{ '/cv/Tatevik_Mkrtchyan_CV.pdf' | relative_url }}">Download CV</a>.
</iframe>

<style>
  .cv-meta {
    margin: 0 0 1rem;
    font-size: 0.9em;
    opacity: 0.8;
  }

  .cv-meta a {
    color: #36a9e1;
    font-weight: bold;
  }
</style>
