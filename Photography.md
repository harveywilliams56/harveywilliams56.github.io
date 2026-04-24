---
layout: page
title: "Photography"
order: 1000
permalink: /photography
---
>To see life; to see the world; to eyewitness great events [...]
>to see and take pleasure in seeing; to see and be amazed; to see and be instructed...

--- Prospectus for LIFE magazine (1936)

I offer portrait and event photography for academic and professional settings, including conferences, talks, and society events. Send me an email if you are interested in booking.

<div>

{% for image in site.static_files %}
    {% if image.path contains 'images/portfolio' %}
	<a href="{{ site.baseurl }}{{ image.path }}">
        <img src="{{ site.baseurl }}{{ image.path }}" alt="image" style="width:180px; padding:5px; border-radius:20px"/>
	</a>
    {% endif %}
{% endfor %}
</div>
