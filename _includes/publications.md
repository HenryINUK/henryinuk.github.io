## Publications

<h4 style="margin:0 10px 0;">Book Chapters</h4>

<ul style="margin:0 0 20px;">
  <li>
    <autocolor><strong>Convolutional Neural Network Accelerators: From Basic Design Principles to Advanced Security Applications</strong></autocolor>
    <br>
    Editor: Basel Halak | <em>Contributing Author (3 Chapters): <strong>Haoyu Wang</strong></em>
    <br>
    Springer, 2025. ISBN: 978-3-032-08513-9
    <a href="https://www.amazon.co.uk/dp/3032085136">[Amazon]</a>
  </li>
</ul>

<h4 style="margin:0 10px 0;">Selected Publications</h4>

<ol class="pub-list">
  {% for publication in site.data.publications.main %}
  <li class="pub-item">
    <span class="pub-badge">{{ publication.conference_short }}</span>
    <div class="pub-body">
      <span class="pub-title">{{ publication.title }}</span>
      <span class="pub-authors">{{ publication.authors }}</span>
      <span class="pub-venue">{{ publication.conference }}{% if publication.notes %}<span class="pub-note">{{ publication.notes }}</span>{% endif %}{% if publication.pdf %} <a href="{{ publication.pdf }}">[PDF]</a>{% endif %}{% if publication.code %} <a href="{{ publication.code }}">[Code]</a>{% endif %}</span>
    </div>
  </li>
  {% endfor %}
</ol>
