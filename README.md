# medinden
    See: https://developers.google.com/maps/documentation/javascript/tutorial#Loading_the_Maps_API
    -->
    <script src="https://maps.googleapis.com/maps/api/js?v=3.exp&sensor=true"></script>

    <script>
// Note: This example requires that you consent to location sharing when
// prompted by your browser. If you see a blank space instead of the map, this
// is probably because you have denied permission for location sharing.

var map;

function initialize() {
  var mapOptions = {
    zoom: 6
  };
  map = new google.maps.Map(document.getElementById('map-canvas'),
      mapOptions);

  // Try HTML5 geolocation
  if(navigator.geolocation) {
    navigator.geolocation.getCurrentPosition(function(position) {
      var pos = new google.maps.LatLng(position.coords.latitude,
                                       position.coords.longitude);

      var infowindow = new google.maps.InfoWindow({
        map: map,
        position: pos,
        content: 'Location found using HTML5.'
      });

      map.setCenter(pos);
    }, function() {
      handleNoGeolocation(true);
    });
  } else {
    // Browser doesn't support Geolocation
    handleNoGeolocation(false);
  }
}

function handleNoGeolocation(errorFlag) {
  if (errorFlag) {
    var content = 'Error: The Geolocation service failed.';
  } else {
    var content = 'Error: Your browser doesn\'t support geolocation.';
  }

  var options = {
    map: map,
    position: new google.maps.LatLng(60, 105),
    content: content
  };

  var infowindow = new google.maps.InfoWindow(options);
  map.setCenter(options.position);
}

google.maps.event.addDomListener(window, 'load', initialize);

    </script>
  </head>
  <body>
  <h1 style="color:green;">Datos Personales </h1>
<p>
Mi nombre es Medin Denvers.
Realice mis estudios primarios y secundarios en el colegio:
<strong>Panama Height International Academy </strong>
</p>

<p>
Actualmente estudio en La Universidad Nacional de Panam&aacute; Licenciatura en Qu&iacute;mica.
</p>

<p>
Pueden encontrarme en Instagram como luxtea_18
  <img src="https://thumbs.gfycat.com/GorgeousSardonicAtlanticridleyturtle-size_restricted.gif" width="50" height="50">
</p>
<a href="https://ibb.co/nmSxFcd"> <img src="https://i.ibb.co/NCzcMjD/md-jpg.jpg" alt="md-jpg" border="0" width="200" height="200"> </a>
    <div id="map-canvas"></div>
  </body>
</html>


