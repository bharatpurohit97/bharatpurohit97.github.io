---
title: About
layout: page
---
![Profile Image]({{ site.url }}/{{ site.picture }})

{% assign cv = site.data.cv.bharatpurohit %}

<div class="md-card no-border">
    <p>{{cv.profile}}</p>
</div>

<div class="md-card shadow">
    <div class="title">
        <h2>Skills</h2>
    </div>
    <div class="content">
        <ul>
            {% for skill in cv.skills %}
            <li>{{ skill }}</li>
            {% endfor %}
        </ul>
    </div>
</div>

<div class="md-card shadow education">
    <div class="title">
        <h2>Education</h2>
    </div>
    {% for entry in cv.education %}
    <dl>
        <dt class="time">{{entry.time}}</dt>
        <dd>
            <h3>{{entry.location}}</h3>
            <p>{{entry.description}}</p>
        </dd>
    </dl>
    {% endfor %}
</div>

<h2 class="employment-heading">Employment History</h2>

<div class="timeline-container">
    {% for employment in cv.employment %}
    <div class="timeline-block">
        <div class="marker"></div>
        <div class="time">{{employment.time}}</div>
        <div class="timeline-content">
            <div class="time">{{employment.time}}</div>
            <h3>{{employment.position}}</h3>
            <span>{{employment.company}} ({{employment.location}})</span>
            <ul>
                {% for responsibility in employment.responsibilities %}
                <li>{{responsibility}}</li>
                {% endfor %}
            </ul>
        </div>
    </div>
    {% endfor %}
</div>


<h2 class="project-heading">Project History</h2>

{% for project in cv.projects %}
<div class="md-card shadow project">
    <div class="meta">
        <div class="team">{{project.team}}</div>
        <div class="time">{{project.time}}</div>
    </div>
    <div class="content">
        <h2>{{project.title}}</h2>
        <ul>
            {% for responsibility in project.responsibilities %}
            <li>{{responsibility}}</li>
            {% endfor %}
        </ul>
    </div>
    <div class="footer">
        <ul>
            {% assign technologies = project.technologies | split: ',' %}
            {% for technology in technologies %}
            <li> {{ technology }}</li>
            {% endfor %}
        </ul>
    </div>
</div>
{% endfor %}
