# Building Overlay
Lớp Building Overlay cho phép người dùng thêm một layer vẽ thêm các Building cùng với các Building có sẵn của Map SDK. Nó chỉ có tác dụng trong chế độ 3D

## 1. BuildingOverlay & BuildingOverlayOption

```javascript
interface BuildingOverlayOptions {
    getUrl: Function // Hàm trả về đường dẫn của Building
    minZoom?: number // Mức zoom tối thiểu của BuildingOverlay
    maxZoom?: number // Mức zoom tối đa của BuildingOverlay
}
````

```javascript
class BuildingOverlay {
    constructor(options?: BuildingOverlayOptions) // Khởi tạo BuildingOverlay từ BuildingOverlayOptions
    getUrl(x: number, y: number, z: number): string // Lấy thông tin đường dẫn của Building theo TileCoordinate
}
```

## 2. Tạo BuildingOverlay
Trước tiên chúng ta cần tạo buildingOverlayOption với hàm getUrl, giá trị của minZoom và maxZoom như phía dưới

***Note: Giá trị của minZoom nếu set thì phải lớn hơn hoặc bằng 17, vì BuildingOverlay chỉ sử dụng trong chế độ 3D của Map***

```javascript
// Tạo buildingOverlayOption
let buildingOverlayOption: map4d.BuildingOverlayOption = {
  getUrl: (x, y, z) => {
    return `https://api.map4d.vn/sdk/tile/v2/${z}/${x}/${y}?mode=3d&key=d9f5568c4c512c562cf0cf9f8ff487ec`
  },
  minZoom: 17,
  maxZoom: 19
}
```

Sau đó chúng ta sẽ tạo BuildingOverlay như sau:

```javascript
// Tạo BuildingOverlay
let buildingOverlay = new map4d.BuildingOverlay(buildingOverlayOption)
// Set Building Overlay vào map cần vẽ
buildingOverlay.setMap(this.map)
```

## 3. Xóa Building Overlay

Để xóa Building Overlay khỏi map ta gán map về null.

```javascript
buildingOverlay.setMap(null)
```

License
-------

Copyright (C) 2016 IOT Link Ltd. All Rights Reserved.
