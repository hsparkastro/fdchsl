---
layout: page
permalink: /publications/
title: Publications
description:
nav: true
nav_order: 2
bibfile: papers
---
<!-- _pages/publications.md -->
<a href="#journal-publications" class="btn btn-outline-dark py-2 px-4 br-2" role="button">Journal Publications</a>
<a href="#book-chapters" class="btn btn-outline-dark py-2 px-4" role="button">Book Chapters</a>
<a href="#conference-publications" class="btn btn-outline-dark py-2 px-4" role="button">Conference Publications</a>
<a href="#tech-report" class="btn btn-outline-dark py-2 px-4" role="button">Technical Reports</a>
<a href="#invited" class="btn btn-outline-dark py-2 px-4" role="button">Invited Presentations</a>
<a href="#theses" class="btn btn-outline-dark py-2 px-4" role="button">Theses</a>

<h4 id="journal-publications">Journal Publications</h4>
  {% bibliography --file inseok_hwang --query @article --template bibtemplate  %}
<h4 id="book-chapters">Book Chapters</h4>
  {% bibliography --file inseok_hwang --query @incollection --template bibtemplate  %}
<h4 id="conference-publications">Conference Publications</h4>
  {% bibliography --file inseok_hwang --query @inproceedings --template bibtemplate  %}
<h4 id="tech-report">Technical Reports</h4>
  {% bibliography --file inseok_hwang --query @techreport --template bibtemplate  %}
<h4 id="invited">Invited Presentations</h4>
  {% bibliography --file invited  --template bibtemplate %}
<h4 id="theses">Theses</h4>
<h5 id="phd-theses">Ph.D. Theses</h5>
  {% bibliography --file theses --query @phdthesis --template bibtemplate  %}
<h5 id="ms-theses">Masters Theses</h5>
  {% bibliography --file theses --query @msthesis --template bibtemplate %}