# Building Overlay Reference

## BuildingOverlay class

`map4d.BuildingOverlay` class

**Constructor** 

Tạo BuildingOverlay với các options được chỉ định

```js
BuildingOverlay(options)
```

- Parameters:
  - options: [BuildingOverlayOptions](/reference/building-overlay?id=buildingoverlayoptions-interface) *required*

**Methods**

| Name           | Parameters                              | Return Value | Description                                                                                    |
|----------------|-----------------------------------------|--------------|------------------------------------------------------------------------------------------------|
| **setMap**     | map: [Map](/reference/map?id=map-class) | `none`       | Hiển thị building overlay lên map, nếu set map là null thì building overlay sẽ bị xóa khỏi map |
| **setVisible** | visibility: boolean                     | `none`       | Ẩn/hiện building overlay trên map                                                              |
| **isVisible**  | `none`                                  | boolean      | Get trạng thái ẩn/hiện của overlay                                                             |

## BuildingOverlayOptions interface

`map4d.BuildingOverlayOptions` interface

Đối tượng BuildingOverlayOptions đùng để xác định các thuộc tính dùng cho BuildingOverlay.

**Properties**

| Name                    | Type     | Description                                                               |
|-------------------------|----------|---------------------------------------------------------------------------|
| **getUrl** *required*   | function | Hàm nhận vào 3 giá trị `x`, `y`, `zoom` và trả về đường dẫn đến Buildings |
| **prefixId** *optional* | string   | Giá trị được thêm vào trước id của những building thuộc overlay.          |
| **visible** *optional*  | boolean  | Nếu là `true` thì building overlay sẽ được hiển thị                       |