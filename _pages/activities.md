---
layout: activities
permalink: /activities/
title: Activities
description: Activities of the GTA-Lab
nav: true
nav_order: 8
---

# GTA-Lab Activities

{% assign sorted_events = site.data.events | sort: "date" | reverse %}
{% for event in sorted_events %}
## {{ event.title }}
🗓 **Date:** {{ event.date }}  
📍 **Location:** {{ event.location }}

{{ event.description }}

<!-- Swiper Slider -->
<div class="swiper mySwiper">
  <div class="swiper-wrapper">
    {% for image in event.images %}
      <div class="swiper-slide">
        <img src="{{ image }}" alt="{{ event.title }}">
      </div>
    {% endfor %}
  </div>
  <!-- Add navigation buttons -->
  <div class="swiper-button-next"></div>
  <div class="swiper-button-prev"></div>
  <!-- Pagination -->
  <div class="swiper-pagination"></div>
</div>

---
{% endfor %}

<!-- Swiper CSS & JS -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/swiper/swiper-bundle.min.css">
<script src="https://cdn.jsdelivr.net/npm/swiper/swiper-bundle.min.js"></script>

<script>
  document.addEventListener("DOMContentLoaded", function() {
    var swiper = new Swiper(".mySwiper", {
      loop: true,
      navigation: {
        nextEl: ".swiper-button-next",
        prevEl: ".swiper-button-prev",
      },
      pagination: {
        el: ".swiper-pagination",
        clickable: true,
      },
    });
  });
</script>
