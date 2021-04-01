---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home-list-orgs
# background: '/img/bg-index.jpg'
---
{% if site.data.orgs %}
<div class="row">
<div class="col-12">
<div class="data-table-wrapper">
<table id="org-list-table" class="table display table-striped">
  <thead>
    <tr>
      <th scope="col">Name</th>
      <th scope="col">Category</th>
      <th scope="col">Social</th>
      <th scope="col">Contact</th>
    </tr>
  </thead>
  <tbody>

{% for link in site.data.links %}
  <tr>
    <td><a href="{{link.Website}}" target="_blank">{{ link.Name }}</a></td>
    <!-- <td>{% for cat in org.category %}{{cat}}, {% endfor %}</td> -->
    {% assign categories = link.Categories | split: "," %}
    <td>{% for cat in categories %} <span class="badge rounded-pill bg-light text-dark">{{cat}}</span> {% endfor %}</td>
    <td>
     {% if link.Facebook != "" %}
      <a class="mr-2" href="{{link.Facebook}}" target="_blank"><i class="fab fa-facebook"><span class="sr-only">Facebook</span></i></a> 
     {% endif %}
     {% if link.Twitter != "" %}
      <a href="{{link.Twitter}}" target="_blank"><i class="fab fa-twitter"><span class="sr-only">Twitter</span></i></a>
     {% endif %}
    </td>
    <td>
     {% if link.Email.size > 0 %}
      <a class="mr-2" href="mailto:{{link.Email}}" target="_blank"><i class="fas fa-envelope"><span class="sr-only">Email</span></i></a> 
     {% endif %}
     {% if link.Phone.size > 0 %}
      <a href="tel:{{link.Phone}}" target="_blank"><i class="fas fa-phone-square-alt"><span class="sr-only">Phone</span></i></a>
     {% endif %}
    </td>
  </tr>
{% endfor %}
  </tbody>
</table>
</div>
</div>
{% else %}
<p> Could not load organizations. </p>
<!-- {% for org in site.data.orgs %}
  <tr>
    <td><a href="{{org.url}}" target="_blank">{{ org.name }}</a></td>
    <td>{% for cat in org.category %}{{cat}}, {% endfor %}</td>
    <td>{% for tag in org.tag %} {{tag}}, {% endfor %}</td>
    <td>
     {% if org.social.facebook != "" %}
      <a class="mr-2" href="{{org.social.facebook}}" target="_blank"><i class="fab fa-facebook"><span class="sr-only">Facebook</span></i></a> 
     {% endif %}
     {% if org.social.twitter != "" %}
      <a href="{{org.social.twitter}}" target="_blank"><i class="fab fa-twitter"><span class="sr-only">Twitter</span></i></a>
     {% endif %}
    </td>
  </tr>
{% endfor %} -->
{% endif %}


