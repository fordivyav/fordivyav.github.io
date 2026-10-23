---
layout: page
permalink: /research/
title: Research
nav: true
nav_order: 2
---

Research projects and publications spanning epilepsy, neurocritical care, machine learning for medicine, and public health.

<div class="research">
{% for e in site.data.research %}
  <div class="row research-entry">
    <div class="col-sm-3 preview">
      {% if e.image %}
        {% assign img_path = e.image | prepend: 'assets/img/' %}
        {% include figure.liquid path=img_path class="preview z-depth-1 rounded" zoomable=true alt=e.title %}
      {% endif %}
    </div>
    <div class="col-sm-9">
      <div class="title">
        {% if e.link %}<a href="{{ e.link }}" target="_blank" rel="noopener">{{ e.title }}</a>{% else %}{{ e.title }}{% endif %}
      </div>
      <div class="periodical">
        {% if e.advisor %}<strong>Advisor:</strong>
          {% if e.advisor_link %}<a href="{{ e.advisor_link }}" target="_blank" rel="noopener">{{ e.advisor }}</a>{% else %}{{ e.advisor }}{% endif %}{% if e.lab %} &middot; {% endif %}{% endif %}
        {% if e.lab %}<strong>Lab:</strong>
          {% if e.lab_link %}<a href="{{ e.lab_link }}" target="_blank" rel="noopener">{{ e.lab }}</a>{% else %}{{ e.lab }}{% endif %}{% endif %}
        <br>
        <strong>Department:</strong> {{ e.department }}
      </div>
      <div class="links">
        {% for t in e.topics %}<span class="badge rounded topic">{{ t }}</span> {% endfor %}
        {% if e.extra_link %}<a href="{{ e.extra_link }}" class="btn btn-sm z-depth-0" role="button" target="_blank" rel="noopener">{{ e.extra_label }}</a>{% endif %}
      </div>
    </div>
  </div>
{% endfor %}
</div>

<style>
  .research-entry { margin-bottom: 1.5rem; }
  .research-entry .title { font-weight: bolder; }
  .research-entry .preview img { width: 100%; min-width: 80px; max-width: 250px; max-height: 220px; object-fit: contain; }
  .research-entry .topic { background-color: var(--global-theme-color); color: white; font-weight: normal; margin-right: 0.25rem; }
  .research-entry .links { margin-top: 0.4rem; }
  @media (max-width: 576px) {
    .research-entry .preview { text-align: center; margin: 0.5rem auto; }
    .research-entry .preview img { min-width: 200px; }
  }
</style>
