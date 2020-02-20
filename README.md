# Map4D SDK

Map4D SDK for Web, written in Javascript.

[![CocoaPods](https://raw.githubusercontent.com/iotlinkadmin/map4d-web-sdk/master/sdk/map4dweb.png)](https://map4d.vn) 

## Important Changelogs

1. Version 1.2.0

- Use api key for api request

2. Version 1.3.1

- Update location array order: [lat, lng] => [lng, lat]

- Render POI on 2D mode

## Installation

1. Download map4dsdk from [here](https://raw.githubusercontent.com/iotlinkadmin/map4d-web-sdk/master/sdk/map4dsdk@1.3.6.prod)

2. Add script to your website
```html
<script src="[PATH]/map4dsdk@[version].js"></script>
```

***Note: SDK script name must contains "map4dsdk@"***

## Using

1. Initialize map with access key

```html
<body>
<div id="map"></div>

<script src="[PATH]/map4dsdk@[version].js"></script>

<script>
  let map = new map4d.Map(document.getElementById("map"),
      {
        center: [105.828042, 21.007651],
        zoom: 17,
        geolocate: true,
        controls :true,
        tilt: 0,        
        accessKey: `${your-key}`
      }
    )
  //set switch mode Auto for automatically switching between 2D & 3D
	map.setSwitchMode(map4d.SwitchMode.Auto)
	map.enable3dMode(true)
</script>

</body>
```

2. Style your view

```css
  <style>
	body {
	  margin: 0px;
	  height: 100%;
	}

	#map {
	  position: absolute;
	  width: 100%;
	  height: 100%;
	  background-color: #f2efe9;
	}
  </style>
  ```

## Document references
[1. Getting started](https://github.com/iotlinkadmin/map4d-web-sdk/blob/master/docs/vi/1.3/0-getting-started.md) 

[2. Map user interaction](https://github.com/iotlinkadmin/map4d-web-sdk/blob/master/docs/vi/1.3/1-map-user-interaction.md) 

[3. Type](https://github.com/iotlinkadmin/map4d-web-sdk/blob/master/docs/vi/1.3/2-type.md)

[4. Map events](https://github.com/iotlinkadmin/map4d-web-sdk/blob/master/docs/vi/1.3/3-map-events.md)

[5. Marker](https://github.com/iotlinkadmin/map4d-web-sdk/blob/master/docs/vi/1.3/4-marker.md)

[6. Marker cluster](https://github.com/iotlinkadmin/map4d-web-sdk/tree/master/docs/vi/1.3/5-marker-cluster.md)

[7. Polyline](https://github.com/iotlinkadmin/map4d-web-sdk/blob/master/docs/vi/1.3/6-polyline.md)

[8. Polygon](https://github.com/iotlinkadmin/map4d-web-sdk/blob/master/docs/vi/1.3/7-polygon.md)

[9. Circle](https://github.com/iotlinkadmin/map4d-web-sdk/blob/master/docs/vi/1.3/8-circle.md)

[10. 3D objects](https://github.com/iotlinkadmin/map4d-web-sdk/blob/master/docs/vi/1.3/9-3d-objects.md)

[11. Tile area](https://github.com/iotlinkadmin/map4d-web-sdk/blob/master/docs/vi/1.3/10-tile-area.md)

[12. Effect](https://github.com/iotlinkadmin/map4d-web-sdk/blob/master/docs/vi/1.3/11-effect-map.md)

[13. LatLngBounds](https://github.com/iotlinkadmin/map4d-web-sdk/blob/master/docs/vi/1.3/12-lat-lng-bounds.md)

[14. Map utils](https://github.com/iotlinkadmin/map4d-web-sdk/blob/master/docs/vi/1.3/13-map-utils.md)

[15. Data layer](https://github.com/iotlinkadmin/map4d-web-sdk/blob/master/docs/vi/1.3/14-data-layer.md)

[16. Leaflet Integrated](https://github.com/iotlinkadmin/map4d-web-sdk/blob/master/docs/vi/1.3/15-leaflet-integrated.md)

[17. Place](https://github.com/iotlinkadmin/map4d-web-sdk/blob/master/docs/vi/1.3/16-place.md)

License
-------

Copyright (C) 2016 IOT Link Ltd. All Rights Reserved.
