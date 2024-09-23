---
title: Learn
layout: page
excerpt: Learn
permalink: /learn/
---

<style>

#study-container {
  padding: 0px;
}

#study-list {
  list-style-type: none;
  margin: 0;
  padding: 0;
}

#study-list li {
  margin-left: 20px;
  font-size: 18px;
  padding: 7px;
  border-radius: 5px;
  background-color: #f8f8f8;
  margin-bottom: 8px;
  transition: background-color 0.3s ease; /* Smooth transition on hover */
}

#study-list li:hover {
  font-weight: bold; /* Bold text on hover */
  font-size: 20px;
  background-color: #007bff; /* Lighter background color on hover */
  cursor: pointer;
}

#study-list li:last-child {
  margin-bottom: 0;
}

#study-list li.level-0 {
  margin-top: 24px; /* Adjust the value based on your preference */
}

#study-list li a {
  /* text-decoration: none; /* Remove underline */
  color: inherit; /* Inherit color from parent (non-link color) */
}

</style>

<div id="study-container">
  <ul id="study-list">
    {% assign studyData = site.data.study %}
    {% assign parent = "" %}
    {% for item in studyData %}
      {% if item.level == 0 %}
        {% assign parent = item.file %}
        {% assign link = site.baseurl | append: "/learn/" | append: item.file | default: "" %}
      {% else %}
        {% assign link = site.baseurl | append: "/learn/" | append: parent | append: "/" | append: item.file | default: parent %}
      {% endif %}
      <li class="level-{{ item.level }}" style="margin-left: {{ item.level | times: 40 }}px; font-size: 22px;">
      <a href="{{ link }}" target="_blank">{{ item.name }}</a>
      </li>
    {% endfor %}
  </ul>
</div>