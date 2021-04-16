<!DOCTYPE html>
<html>
<body onload="getLocation()">

<p><h1>Maria's Photos</h1></p>
<img source="screenshot1.jpg">
<!-- <button onclick="getLocation()">Try It</button> -->

<p id="demo"></p>

<script>
var x = document.getElementById("demo");

function getLocation() {
  if (navigator.geolocation) {
    navigator.geolocation.getCurrentPosition(showPosition, showError);
  } else {
    x.innerHTML = "Geolocation is not supported by this browser.";
  }
}

function showPosition(position) {
  x.innerHTML = "<img source='screenshot2.jpg'>";
}

function showError(error) {
  switch(error.code) {
    x.innerHTML = "<img source='screenshot1.jpg'>";
    case error.PERMISSION_DENIED:
      x.innerHTML = "User denied the request for Geolocation."
      break;
    case error.POSITION_UNAVAILABLE:
      x.innerHTML = "Location information is unavailable."
      break;
    case error.TIMEOUT:
      x.innerHTML = "The request to get user location timed out."
      break;
    case error.UNKNOWN_ERROR:
      x.innerHTML = "An unknown error occurred."
      break;
  }
}
</script>

</body>
</html>
