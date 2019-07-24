---
layout: map
---

<style>
  #map {
    height: 500px;
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

  var infowindow = new google.maps.InfoWindow();

  // When the user clicks, open an infowindow
map.data.addListener('click', function(event) {
	var commonName = event.feature.getProperty("SPECIES_01");
  var scienceName = event.feature.getProperty("SPECIES_LA");
  var heightRange = event.feature.getProperty("HEIGHT_RAN");
  var comment = event.feature.getProperty("TREE_COMME");
  var address = event.feature.getProperty("ADDRESS_NU");
  var myHTML = ('Common:' + commonName + "<br />" + 'Scientific:' + scienceName + "<br />" + " heightRange + comment + address);
	infowindow.setContent("<div style='width:150px;'>"+myHTML+"</div>");
	// position the infowindow on the marker
	infowindow.setPosition(event.feature.getGeometry().get());
	// anchor the infowindow on the marker
	infowindow.setOptions({pixelOffset: new google.maps.Size(0,-30)});
	infowindow.open(map);
});

}
</script>


<script async defer
    src="https://maps.googleapis.com/maps/api/js?key=AIzaSyDa6DZeRE5sjojvDXT-Rh4npQgfci2XTQ8&callback=initMap">
</script>
