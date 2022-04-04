## Alumni
{% assign sorted = (site.alumni | sort: "enddate") | reverse %}
{% for member in sorted %}
<hr>

<div id = "{{member.name}}" style="padding-top: 60px; margin-top: -60px;">

<strong>{{member.name}}</strong> - <em>{{member.position}}</em> <br>
{% if member.pronouns %}
    <em>{{member.pronouns}}</em> <br>
{% endif %}
<!-- Dates -->
{% assign start = member.startdate | date:"%Y" %}
{% assign end = member.enddate | date:"%Y" %}
{% if start == end %}
{{ start }}<br>
{% else %}
{{ start }} - {{ end }}<br>
{% endif %}
{% if member.subsequent %}
    Subsequently: {{ member.subsequent }}<br>
{% endif %}

{% if member.cv %} <a href="{{member.cv}}" alt="{{member.name}} CV">curriculum vitae</a><br>{% endif %}
{% if member.email %}
{% unless member.email contains "scripps.edu" %}
<em>{{member.email}}</em> <br>
{% endunless %}
{%endif%}
{% if member.website %}
    <a style="overflow-wrap: break-word;" href= "{{member.website}}">{{member.website}}</a> <br>
{% endif %}
{% if member.orcid %}
    <a href="http://orcid.org/{{member.orcid}}" class="align-middle"> 
    <img class="inline-block mem-logo" src="/static/img/logo/orcid_logo.svg">
{{member.orcid}}
</a> <br>
{% endif %}
{% if member.linkedin %}
    <a href= "http://www.linkedin.com/in/{{member.linkedin}}"> 
    <img class="inline-block mem-logo" src="/static/img/logo/linkedin_logo.svg">
    LinkedIn </a> <br>
{% endif %}
{% if member.scholar %}
    <a href= "http://scholar.google.com/citations?user={{member.scholar}}">
    <img class="inline-block mem-logo" src="/static/img/logo/gscholar_logo.svg">
    Scholar Citations </a> <br>
{% endif %}
{% if member.twitter %}
    <a href= "http://twitter.com/{{member.twitter}}">
    <img class="inline-block mem-logo" src="/static/img/logo/twitter_logo.svg">
    @{{member.twitter}} 
    </a> <br>
{% endif %}
{% if member.github %}
    <a href= "http://github.com/{{member.github}}"> {% octicon mark-github %} {{member.github}} </a> <br>
{% endif %}

</div>
{% endfor %}
<br>

## Interns

{% assign sorted = (site.interns | sort: "enddate") | reverse %}
{% for intern in sorted %}
<hr>

<div id = "{{intern.name}}" style="padding-top: 60px; margin-top: -60px;">
<strong>{{intern.name}}</strong><br>
{% if intern.pronouns %}<em>{{intern.pronouns}}</em><br>{% endif %}
<!-- Dates -->
{% assign start = intern.startdate | date:"%Y" %}
{% assign end = intern.enddate | date:"%Y" %}
{% if start == end %}
{{ start }}<br>
{% else %}
{{ start }} - {{ end }}<br>
{% endif %}
{% if intern.subsequent %}
Subsequently: {{intern.subsequent}}<br>
{% endif %}

{% endfor %}
</div>
