---
layout: page
permalink: /publications/
title: publications
description: Generated from NASA ADS. First-author papers are listed separately.
nav: true
nav_order: 2
---

<!-- _pages/publications.md -->

A full list of publications can be found on [NASA ADS](https://ui.adsabs.harvard.edu/search/fq=%7B!type%3Daqp%20v%3D%24fq_database%7D&fq_database=(database%3Aastronomy%20OR%20database%3Aphysics)&q=%20author%3A%22Rocha%2C%20Kyle%20Akira%22%20year%3A2015-&sort=date%20desc%2C%20bibcode%20desc&p_=0).

{% include bib_search.liquid %}

## First-Author Papers

<div class="publications">

{% bibliography --query @*[selected=true] %}

</div>

## Co-Authored Papers

<div class="publications">

{% bibliography --query @*[selected!=true] %}

</div>
