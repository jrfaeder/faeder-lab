---
title: Software
nav:
  order: 2
  tooltip: Software, teaching materials, and resources
---

# {% include icon.html icon="fa-solid fa-code" %}Software

All of our software is free and open source.
Most of it lives in the [RuleWorld](https://github.com/RuleWorld) organization on GitHub.
Questions and bug reports are welcome on the individual repositories.

{% include tags.html tags="software, teaching" %}

{% include search-info.html %}

{% include section.html %}

## Featured

{% include list.html component="card" data="projects" filter="group == 'featured'" %}

{% include section.html %}

## More tools

{% include list.html component="card" data="projects" filter="!group" style="small" %}
