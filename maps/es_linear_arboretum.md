---
layout: default
---

<style>
  #map {
    height: 400px;
    width: 100%;
   }
</style>


# Eureka Springs Linear Arboretum

<div id="map"></div>
<script>

function initMap() {
  var options = {
    zoom: 13,
    center:{lat:36.4026,lng:-93.7360}
  }  

  var map = new google.maps.Map(document.getElementById('map'), options);

}
</script>


<script async defer
    src="https://maps.googleapis.com/maps/api/js?key=AIzaSyDa6DZeRE5sjojvDXT-Rh4npQgfci2XTQ8&callback=initMap">
</script>
