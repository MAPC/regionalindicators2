---
layout: default
---

{% for topicarea in site.topicareas %}
  <h1> > Topic Area: {{topicarea.title}}</h1>
  {{topicarea.content}}
  {% for subject in topicarea.subjects %}
    {% assign subjects = site.subjects | where: "title", subject %}
    {% for subject in subjects %}
      <h2> >> Subject: {{subject.title}}</h2>
      {{subject.content}}

      {% for indicator in subject.indicators %}
        {% assign indicators = site.indicators | where: "title", indicator %}
        {% for indicator in indicators %}
          <h3> >>> Indicator: {{indicator.title}}</h3>
          {{indicator.content}}
        {% endfor %}
      {% endfor %}

      

    {% endfor %}
  {% endfor %}
{% endfor %}

