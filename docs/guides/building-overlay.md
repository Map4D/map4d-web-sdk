# Building Overlay

Building overlay là một loại overlay cho phép người dùng hiển thị các building từ nhiều nguồn khác nhau lên bản đồ, kết hợp với building sẵn có của Map4D

Building overlay chỉ hiển thị ở chế độ 3D.

## Add Building overlay

Để thêm 1 building overlay vào map cần tạo mới 1 đối tượng của lớp [BuildingOverlay](reference/building-overlay?id=buildingverlay-class) sau đó set `map` cho building overlay đó.

Hàm khởi tạo của lớp [BuildingOverlay](reference/building-overlay?id=buildingoverlay-class) nhận vào một đối tượng [BuildingOverlayOptions](reference/building-overlay?id=buildingoverlayoptions-interface) có các tham số như sau:

| No | Property | Type | Requied | Description | Example |
|:--:|----------|------|:-------:|-------------|---------|
| 1 | getUrl | function | YES | Hàm nhận vào 3 giá trị `x`, `y`, `zoom` và trả về đường dẫn đến Buildings | `function(x, y, zoom) {`<br>` return "http://example.com/zoom/x/y/buildings"`<br>`}` |
| 2 | prefixId | string | NO | Giá trị được thêm vào trước id của những building thuộc building overlay.<br>Dùng để tránh nhầm lẫn trong trường hợp trùng id với building của Map4D hay các building overlay khác | `"building_overlay_"` |
| 3 | visible | boolean | NO | Nếu `true` thì building overlay sẽ được hiển thị | `true` |

### Tạo mới Building overlay

```js
let options = {
  getUrl: function (x, y, zoom) {
    return `https://example.com/${zoom}/${x}/${y}`
  },
  prefixId: "building-1_"
  visible: true
}
let overlay = new map4d.BuildingOverlay(options)
```

### Add Building overlay lên Map

Để vẽ building overlay lên map, ta set map cho building overlay bằng hàm `setMap`

```js
overlay.setMap(map)
```

### Remove Building overlay

Để xóa building overlay khỏi map, ta gọi hàm `setMap` và truyền vào giá trị `null`

```js
overlay.setMap(null)
```

### Ẩn/Hiện Building Overlay

Gọi hàm `setVisible(boolean)` để ẩn/hiện building overlay.

Chú ý: Mặc dù building overlay không hiển thị nhưng quá trình tải các building vẫn diễn ra

```js
overlay.setVisible(false)
```

## Sự kiện đối với building thuộc building overlay

Các sự kiện đối với building thuộc building overlay phát sinh tương tự với building của Map4D, việc xử lý được diễn ra ngay tại hàm xử lý sự kiện của Map4D. Xem [Events](/guides/map-events)

## API Response cho hàm getUrl
Để sử dụng được tính năng Building Overlay trên Map4D Map SDK, bạn cần 1 API nhận 3 thông số của một `Map Tile` là `x`, `y`, `zoom` và dữ liệu trả về kiểu `JSON` theo cấu trúc sau:

```json
{
  "code": "ok",
  "message": "message",
  "result": {
    "objects": [
      {
        "id": "string",
        "name": "string",        
        "location": {
          "lng": 0,
          "lat": 0
        },
        "scale": 0,
        "bearing": 0,
        "elevation": 0,
        "camera": {
          "zoom": 0,
          "bearing": 0,
          "tilt": 0
        },
        "types": [
          "string"
        ],
        "minZoom": 0,
        "maxZoom": 0,
        "startDate": "1569801600000",
        "endDate": "1569901600000",
        "model": {
          "id": "string",
          "type": "Object", //or Polygon
          "objName": "string",
          "objUrl": "string",
          "textureName": "string",
          "textureUrl": "string",
          "color": "string",
          "height": 0,
          "coordinates": [
            {
              "lng": 0,
              "lat": 0
            }
          ]
        }
      }
    ]
  }
}
```

> Gợi ý thiết kế database  
> Cần 2 collection để lưu thông tin các tile map và thông tin đối tượng:  
> ## Tile Collection
> ```json
> {
>   "id": "string",
>   "x": "number",
>   "y": "number",
>   "zoom": "number",
>   "objects": ["objectId"]
> }
> ```  
> ## Object Collection  
> ```json
>{
>        "id": "string",
>        "name": "string",        
>        "location": {
>          "lng": 0,
>          "lat": 0
>        },
>        "scale": 0,
>        "bearing": 0,
>        "elevation": 0,
>        "camera": {
>          "zoom": 0,
>          "bearing": 0,
>          "tilt": 0
>        },
>        "types": [
>          "string"
>        ],
>        "minZoom": 0,
>        "maxZoom": 0,
>        "startDate": "1569801600000",
>        "endDate": "1569901600000",
>        "model": {
>          "id": "string",
>          "type": "Object", //or Polygon
>          "objName": "string",
>          "objUrl": "string",
>          "textureName": "string",
>          "textureUrl": "string",
>          "color": "string",
>          "height": 0,
>          "coordinates": [
>            {
>              "lng": 0,
>              "lat": 0
>            }
>          ]
>        }
>}
> ```  