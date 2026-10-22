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

<style>
.portfolio {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    grid-auto-flow: dense;
    gap: 10px;
}

.portfolio a {
    display: block;
    min-width: 0;
    aspect-ratio: 2 / 3;
    overflow: hidden;
    border-radius: 20px;
}

.portfolio a.landscape {
    grid-column: span 2;
    aspect-ratio: auto;
}

.portfolio img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
}

@media (max-width: 600px) {
    .portfolio {
        grid-template-columns: 1fr;
    }

    .portfolio a.landscape {
        grid-column: span 1;
        aspect-ratio: 2 / 3;
    }
}
</style>

<div class="portfolio">
{% for image in site.static_files %}
    {% if image.path contains 'images/portfolio' %}
        <a href="{{ site.baseurl }}{{ image.path }}">
            <img src="{{ site.baseurl }}{{ image.path }}" alt="image">
        </a>
    {% endif %}
{% endfor %}
</div>

<script>
document.querySelectorAll('.portfolio img').forEach(img => {
    function classify() {
        const ratio = img.naturalWidth / img.naturalHeight;

        // Only genuinely landscape images span two columns
        if (ratio > 1.2) {
            img.parentElement.classList.add('landscape');
        }
    }

    if (img.complete && img.naturalWidth) {
        classify();
    } else {
        img.addEventListener('load', classify);
    }
});
</script>
