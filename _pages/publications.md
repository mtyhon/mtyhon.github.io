---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---
## Lead author papers
{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}


---
---
---

## Contributed Detections
{% for post in site.publications_det reversed %}
  {% include archive-single.html %}
{% endfor %}


---
---
---

## Contributed Evolutionary States
{% for post in site.publications_evstate reversed %}
  {% include archive-single.html %}
{% endfor %}


---
---
---

## Contributed Observational Data
{% for post in site.publications_obs reversed %}
  {% include archive-single.html %}
{% endfor %}
