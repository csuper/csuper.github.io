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
var map;
function initMap() {
  map = new google.maps.Map(document.getElementById('map'), {
    zoom: 13,
    center: {lat:36.4026,lng:-93.7360}
  });

  // NOTE: This uses cross-domain XHR, and may not work on older browsers.
  map.data.loadGeoJson(
      'https://csuper.us/maps/ES_LA_Full.geojson');

  // Set the stroke width, and fill color for each polygon
  map.data.setStyle({
      icon: 'https://csuper.us/assets/img/tree.png'
    });

}
</script>


<script async defer
    src="https://maps.googleapis.com/maps/api/js?key=AIzaSyDa6DZeRE5sjojvDXT-Rh4npQgfci2XTQ8&callback=initMap">
</script>
