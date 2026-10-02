---
layout: plain
title: Teaching
permalink: /teaching/
redirect_from:
  - /education/
slug: teaching
no_groups: true
sitemap: false
image_mentorship: /teaching/mentoring.jpg
caption_mentorship: "Mentoring Matters panel discussion in Yerevan"
image_students: /teaching/teaching_kids.jpg
caption_students: "Teaching a class in Armenia"
---

<p class="intro">I have more than five years of experience in education, as a teacher, a teacher's mentor, an education specialist and a content writer. Most of that work was in Armenia, in both formal and non-formal settings, and much of it came down to one thing: getting good teaching to students who would not otherwise have had it.</p>

<p class="lead-in">Here is what I have been part of.</p>

<!-- Each section is a banner photo that links to its subpage, with the subpage's
     own name laid over it, then a short description. The photo and the name on it
     are one link, so clicking anywhere on the image navigates there. -->

<section class="project">
  <figure class="project-media break-layout">
    <a class="media-link" href="/teaching/mentorship/">
      <div class="media-frame">
        <img src="{{ page.image_mentorship }}" alt="Mentoring Matters panel discussion">
        <span class="media-title">Mentorship and trainings</span>
      </div>
    </a>
    <figcaption>{{ page.caption_mentorship }}</figcaption>
  </figure>
  <p>I was selected for a qualification program run by the Ministry of Education of Armenia with UNICEF and Teach for Armenia, and trained as part of the first generation of mentors responsible for the country's transition to inclusive education. As an inclusive education specialist I mentored more than 60 teachers across over five schools, helping them build classrooms where children of all abilities learn together. I have also mentored teenagers through startup initiatives, and I speak at conferences and workshops on education.</p>
  <p class="learn-more"><a href="/teaching/mentorship/">Learn more about it</a></p>
</section>

<section class="project">
  <figure class="project-media break-layout">
    <a class="media-link" href="/teaching/students/">
      <div class="media-frame">
        <img src="{{ page.image_students }}" alt="Teaching a class in Armenia">
        <span class="media-title">Work with students</span>
      </div>
    </a>
    <figcaption>{{ page.caption_students }}</figcaption>
  </figure>
  <p>I started teaching in my second year of undergraduate studies, at TUMO Center for Creative Technologies, building robotics content and running workshops for teenagers. After that I taught physics and led the astronomy club at Shirakatsy Scientific Educational Complex. When the COVID lockdown shut Armenia's schools, I was one of 20 teachers chosen to build the country's official remote physics lessons, and I created more than 50 video lessons that the Ministry of Education accredited as part of the national curriculum.</p>
  <p class="learn-more"><a href="/teaching/students/">Learn more about it</a></p>
</section>

<style>
  .intro {
    margin: 0 0 1rem;
    line-height: 1.45;
  }

  .lead-in {
    font-weight: bold;
    margin: 0 0 1.25rem;
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

  .learn-more a {
    color: #36a9e1;
    font-weight: bold;
    text-decoration: underline;
    text-decoration-thickness: 2px;
    text-underline-offset: 3px;
  }

  .learn-more a:hover {
    filter: brightness(1.2);
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
