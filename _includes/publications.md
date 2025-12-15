## Publications

<h4 style="margin:0 10px 0;">Selected Publications</h4>

<ul style="margin:0 0 5px;">
  {% for publication in site.data.publications.main %}
  <li>
    <autocolor>{{ publication.title }}</autocolor>
    <br>
    <em>{{ publication.authors }}</em>
    <br>
    {{ publication.conference }}
    {% if publication.notes %}
    <span style="color:#9a9a9a;"> ({{ publication.notes }})</span>
    {% endif %}
    {% if publication.pdf %}
    <a href="{{ publication.pdf }}">[PDF]</a>
    {% endif %}
    {% if publication.code %}
    <a href="{{ publication.code }}">[Code]</a>
    {% endif %}
  </li>
  {% endfor %}
</ul>
