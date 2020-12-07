# POI Overlay References

## POIOverlay class

`map4d.POIOverlay` class

**Constructor** 

Tạo POIOverlay với các options được chỉ định

```js
POIOverlay(options)
```

- Parameters:
  - options: [POIOverlayOptions](/reference/poi-overlay?id=poioverlayoptions-interface) *required*

**Methods**

| Name           | Parameters                              | Return Value | Description                                                                          |
|----------------|-----------------------------------------|--------------|--------------------------------------------------------------------------------------|
| **setMap**     | map: [Map](/reference/map?id=map-class) | `none`       | Hiển thị POI overlay lên map, nếu set map là null thì POI overlay sẽ bị xóa khỏi map |
| **setVisible** | visibility: boolean                     | `none`       | Ẩn/hiện POI overlay trên map                                                         |
| **isVisible**  | `none`                                  | boolean      | Get trạng thái ẩn/hiện của overlay                                                   |


## POIOverlayOptions interface

`map4d.POIOverlayOptions` interface

Đối tượng POIOverlayOptions đùng để xác định các thuộc tính dùng cho POIOverlay.

**Properties**

| Name                    | Type     | Description                                                          |
|-------------------------|----------|----------------------------------------------------------------------|
| **getUrl** *required*   | function | Hàm nhận vào 3 giá trị `x`, `y`, `zoom` và trả về đường dẫn đến POIs |
| **prefixId** *optional* | string   | Giá trị được thêm vào trước id của những POI thuộc overlay.          |
| **visible** *optional*  | boolean  | Nếu là `true` thì POI overlay sẽ được hiển thị                       |