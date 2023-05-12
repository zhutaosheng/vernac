---
layout: default
---

## Search


<script async src="https://cse.google.com/cse.js?cx=b0d7ff12adcb24b8f">
</script>

<div class="gcse-search"></div>

## New Search

---
layout: page
---

{{ content }}

<form onsubmit="return false;">
  <input type="input" id="search" class="search-input" placeholder="{{ site.data.text[site.locale].search_placeholder_text | default: 'Enter your search term...' }}" autofocus>
</form>

<div id="results"></div>