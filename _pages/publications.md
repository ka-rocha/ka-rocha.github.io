---
layout: page
permalink: /publications/
title: publications
description: Generated from NASA ADS. First-author papers are listed separately.
nav: true
nav_order: 2
---

<!-- _pages/publications.md -->

{% include bib_search.liquid %}

## First-Author Papers

<div class="publications">

{% bibliography --query @*[selected=true] %}

</div>

## Co-Authored Papers

<div class="publications">

{% bibliography --query @*[selected!=true] %}

</div>
