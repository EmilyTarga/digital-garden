---
layout: page
title: Home
id: home
permalink: /
---

# Oie 🌱 Tudo bem? 

<p style="padding: 3em 1em; background: #f5f7ff; border-radius: 4px; margin-top: 0.5em">
  Olá, eu sou Emily May, uma programadora que ama muito mais do que apenas escrever código. 
  <br>
  <br>
  Neste espaço, compartilho meus pensamentos e reflexões sobre livros que me emocionam, filmes que me fazem questionar, músicas que tocam minha alma, e filosofias que moldam minha visão de mundo.
  <br>
  <br>
  <strong>AI-Generated Description 🤖 <br> Não consigo pensar em me descrever em um paragrafo.</strong> 
</p>

<strong>Últimos Posts</strong>
<ul>
  {% assign recent_posts = site.posts | sort: "last_modified_at_timestamp" | reverse %}
  {% for note in recent_posts limit: 5 %}
    <li>
      {{ note.last_modified_at | date: "%Y-%m-%d" }} — <a class="internal-link" href="{{ site.baseurl }}{{ note.url }}">{{ note.title }}</a>
    </li>
  {% endfor %}
</ul>

<strong>Categorias</strong>

<div class="accordion" id="accordionExample">
 
{% for category in site.categories %}
    {% capture category_name %}{{ category | first }}{% endcapture %}
    <div class="accordion-item mb-3">
    <h2 class="accordion-header">
      <button class="accordion-button" type="button" data-bs-toggle="collapse" data-bs-target="#collapse_{{ category_name | slugize }}" aria-expanded="true" aria-controls="collapse_{{ category_name | slugize }}">
        {{ category_name }} 
      </button>
    </h2>
    <div id="collapse_{{ category_name | slugize }}" class="accordion-collapse collapse show" data-bs-parent="#accordionExample">
      <div class="accordion-body">
      <ul>
        {% assign recent_notes = site.categories[category_name] | sort: "last_modified_at_timestamp" | reverse %}
        {% for note in recent_notes %}
          <li>
            {{ note.last_modified_at | date: "%Y-%m-%d" }} — <a class="internal-link" href="{{ site.baseurl }}{{ note.url }}">{{ note.title }}</a>
          </li>
        {% endfor %}
      </ul>
      </div>
    </div>
  </div>

 {% endfor %}
</div>
