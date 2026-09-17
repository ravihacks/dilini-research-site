---
layout: base.njk
title: Contact
description: Contact Dr Dilini Perera for research, collaboration and academic enquiries.
permalink: /contact/index.html
---
<section class="page-hero container narrow">
<p class="eyebrow">Contact</p>
<h1>Research and collaboration enquiries.</h1>
<p class="lede">For research collaboration, academic discussion or professional enquiries, use the contact links below.</p>
</section>

<section class="section">
<div class="container narrow contact-card">
<h2>Connect</h2>
<p>Add an email address, Google Scholar, ORCID and LinkedIn in <code>src/_data/site.json</code>. Links will then appear automatically in the site footer.</p>
{% if site.email %}<p><a class="button" href="mailto:{{ site.email }}">Email {{ site.shortName }}</a></p>{% endif %}
<p class="muted">Location: {{ site.location }}</p>
</div>
</section>
