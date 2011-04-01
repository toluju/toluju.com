---
layout: page
---

This is a sample of my pictures. More can be found on my [Picasa page](http://www.flickr.com/toluju).

<div id="imagelist"></div>

<script type="text/javascript">
$(function() {
  $.getJSON("https://picasaweb.google.com/data/feed/api/user/tobias.jungen?kind=photo&max-results=24&alt=json&thumbsize=160c&fields=entry(title,link[%40rel=%22http%3A%2F%2Fschemas.google.com%2Fphotos%2F2007%23canonical%22],media:group/media:thumbnail)&callback=?", function(data) {
    var imagelist = $("#imagelist");
    $.each(data.feed.entry, function(i,entry) {
      imagelist.append("<a href='" + entry.link[0].href + "' title='" + entry.title.$t + "'><img src='" + entry.media$group.media$thumbnail[0].url + "' alt='" + entry.title.$t + "'/></a>");
    });
  });
});
</script>
