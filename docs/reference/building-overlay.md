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
| **getPrefixId**| `none`                                  | string       | Get prefixId                                                                                   |

## BuildingOverlayOptions interface

`map4d.BuildingOverlayOptions` interface

Đối tượng BuildingOverlayOptions đùng để xác định các thuộc tính dùng cho BuildingOverlay.

**Properties**

| Name                    | Type     | Description                                                               |
|-------------------------|----------|---------------------------------------------------------------------------|
| **getUrl** *required*   | function | Hàm nhận vào 3 giá trị `x`, `y`, `zoom` và trả về đường dẫn đến Buildings |
| **prefixId** *optional* | string   | Giá trị được thêm vào trước id của những building thuộc overlay.          |
| **visible** *optional*  | boolean  | Nếu là `true` thì building overlay sẽ được hiển thị                       |


## BuildingData interface

`map4d.BuildingData` interface

Đối tượng BuildingData dùng để xác định các thuộc tính của building

**Properties**

| Name                       | Type                                           | Description                                                                                                                                            |
|----------------------------|------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
| **id** *required*          | string                                         | Building ID                                                                                                                                            |
| **name** *required*        | string                                         | Tên Building                                                                                                                                           |
| **position** *required*    | [ILatLng](/reference/coordinates?id=ilatlng)   | Vị trí hiển thị building trên bản đồ                                                                                                                   |
| **modelType** *optional*   | string                                         | Kiểu model của building (`Object` hoặc `Polygon`),<br>Nếu là `Object` thì model lấy từ `modelUrl`, `Polygon` thì model được dựng dựa vào `coordinates` |
| **modelName** *optional*   | string                                         | Tên model của building                                                                                                                                 |
| **modelUrl** *optional*    | string                                         | Đường dẫn URL để lấy dữ liệu model cho Building                                                                                                        |
| **textureName** *optional* | string                                         | Tên texture của building                                                                                                                               |
| **textureUrl** *optional*  | string                                         | Đường dẫn URL để lấy dữ liệu texture cho Building                                                                                                      |
| **coordinates** *optional* | [ILatLng[]](/reference/coordinates?id=ilatlng) | Vị trí những tọa độ của building dạng polygon                                                                                                          |
| **height** *optional*      | number                                         | Chiều cao của building (đơn vị: mét)                                                                                                                   |
| **scale** *optional*       | number                                         | Tỉ lệ hiển thị của building so với kích thước thực tế                                                                                                  |
| **bearing** *optional*     | number                                         | Góc quay của building khi được vẽ ra trên bản đồ (đơn vị: độ)                                                                                          |
| **elevation** *optional*   | number                                         | Độ cao của building so với mực nước biển (đơn vị: mét)                                                                                                 |
| **types** *optional*       | string[]                                       | Những kiểu của building                                                                                                                                |
| **startDate** *optional*   | number                                         | Ngày bắt đầu hiển thị building                                                                                                                         |
| **endDate** *optional*     | number                                         | Ngày kết thúc hiển thị building                                                                                                                        |