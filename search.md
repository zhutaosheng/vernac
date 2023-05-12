---
layout: default
---

## Search


<script async src="https://cse.google.com/cse.js?cx=b0d7ff12adcb24b8f">
</script>

<div class="gcse-search"></div>



<form onsubmit="return false;">
  <input type="input" id="search" class="search-input" placeholder="{{ site.data.text[site.locale].search_placeholder_text | default: 'Enter your search term...' }}" autofocus>
</form>

<div id="results"></div>


## new test

<form onsubmit="search(); return false;">
  <input type="text" id="search" class="search-input" placeholder="Enter your search term..." autofocus>
  <button type="submit">Search</button>
</form>

<div id="results"></div>

<script>
  function search() {
    // Get the search query from the input field
    var query = document.getElementById("search").value;
    
    // Perform the search
    var matches = document.querySelectorAll("body *:not(script):not(style)");
    var count = 0;
    for (var i = 0; i < matches.length; i++) {
      var element = matches[i];
      var text = element.innerText || element.textContent || "";
      if (text.toLowerCase().indexOf(query.toLowerCase()) !== -1) {
        count++;
        var html = element.innerHTML;
        html = html.replace(new RegExp(query, "gi"), "<span class='highlight'>$&</span>");
        element.innerHTML = html;
      }
    }
    
    // Display the search results
    var results = document.getElementById("results");
    results.textContent = count + " matches found.";
  }
</script>

<style>
  .highlight {
    background-color: yellow;
    font-weight: bold;
  }
</style>
