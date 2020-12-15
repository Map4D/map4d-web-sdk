# Map4D Web SDK

Map4D SDK for Web, written in Javascript.

[![Map4D Web SDK](https://raw.githubusercontent.com/map4d/map4d-web-sdk/master/sdk/map4dweb.png)](https://map4d.vn) 

## Installation

```JavaScript
<script defer src="https://api.map4d.vn/sdk/map/js?version={SDK_VERSION}&key={YOUR_API_KEY}&callback={CALLBACK_FUNCTION}"></script>
```

## Hello, World

```HTML
<!DOCTYPE html>
<html>
<head>
  <script defer src="https://api.map4d.vn/sdk/map/js?version={SDK_VERSION}&key={YOUR_API_KEY}&callback={CALLBACK_FUNCTION}"></script>
</head>
<body>
  <div id="map" style="width:100%;height:250px;"></div>
  <script>
    function initMap() {
      let options = {
        center: {lat: 16.072163491469226, lng: 108.22690536081757},
        zoom: 15,
        controls: true
      }
      let map = new map4d.Map(document.getElementById("map"), options)
    }
  </script>
</body>
</html>
```

## Document references

http://docs.map4d.vn/map4d-web-sdk

License
-------
Copyright (C) 2020 IOT Link Ltd. All Rights Reserved.
