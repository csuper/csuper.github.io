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

  var uluru = {lat: 36.4026, lng: -93.7360};

  var map = new google.maps.Map(document.getElementById('map'), {zoom: 8, center: uluru});

  var marker = new google.maps.Marker({position: uluru, map: map});
}
</script>


<script async defer
    src="https://maps.googleapis.com/maps/api/js?key=AIzaSyDa6DZeRE5sjojvDXT-Rh4npQgfci2XTQ8&callback=initMap">
</script>
