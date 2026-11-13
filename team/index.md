---
title: Team
nav:
  order: 3
  tooltip: Lab members and alumni
---

# {% include icon.html icon="fa-solid fa-users" %}Team

{% include section.html %}

{% include list.html data="members" component="portrait" filter="role == 'principal-investigator'" %}

## Postdoctoral fellows

{% include list.html data="members" component="portrait" filter="role == 'postdoc'" %}

## Graduate students

{% include list.html data="members" component="portrait" filter="role == 'phd'" %}

## Master's students

{% include list.html data="members" component="portrait" filter="role == 'masters'" %}

## Undergraduates

{% include list.html data="members" component="portrait" filter="role == 'undergrad'" %}

{% include section.html dark=true %}

## Join the lab

We welcome inquiries from prospective postdocs, graduate students, and undergraduates with backgrounds in biology, physics, chemistry, mathematics, computer science, or engineering who want to work on quantitative models of living systems.

- **Graduate students:** rotate through the [Joint CMU–Pitt PhD Program in Computational Biology](https://www.compbio.cmu.edu/) or other Pitt graduate programs.
- **Postdocs and undergraduates:** email Dr. Faeder with a CV and a short description of your interests.

{%
  include button.html
  type="email"
  text="faeder@pitt.edu"
  link="faeder@pitt.edu"
%}

{% include section.html %}

## Alumni

<div class="alumni-list">
{% for a in site.data.alumni %}
<div class="alumni-item">
  <strong>{{ a.name }}</strong>{% if a.orcid %} <a href="https://orcid.org/{{ a.orcid }}" aria-label="ORCID">{% include icon.html icon="fa-brands fa-orcid" %}</a>{% endif %}<br>
  <span class="alumni-role">{{ a.role }}</span>
  {% if a.now %}<br><span class="alumni-now">Now: {{ a.now }}</span>{% endif %}
</div>
{% endfor %}
</div>
