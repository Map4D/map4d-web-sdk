# Sự kiện Map4D-SDK
Hướng dẫn sử dụng các sự kiện của Map4D SDK.

## 1. Giới thiệu chung

  > Chú ý: Nếu bạn đăng ký sự kiện trên map thì phải remove chúng khi không còn sử dụng để cải thiện hiệu năng cho map.
  Chi tiết hướng dẫn có ở phần 2.

  **1.1. cameraWillChange**
  - Được gọi khi một trong các thông số camera (tâm, góc nghiêng, góc quay, mức zoom) của map chuẩn bị thay đổi.

  **1.2. cameraChanging**
  - Được gọi khi một trong các thông số camera (tâm, góc nghiêng, góc quay, mức zoom) của map đang thay đổi.

  **1.3. idle**
  - Được gọi khi các thông số camera (tâm, góc nghiêng, góc quay, mức zoom) của map kết thúc sự thay đổi.

  **1.4. click**
  - Được gọi khi có sự kiện click trên map , click trên map có độ ưu tiên thấp nhất. (thứ tự ưu tiên nhận click: Marker, Polyline, Polygon, Object, Map).

  **1.5. dblClick**
  - Được gọi khi click 2 lần chuột trái vào map.

  **1.6. drag**
  - Được gọi khi map đang được giữ và kéo chuột trái.

  **1.7. dragEnd**
  - Được gọi khi map kết thúc giữ và kéo chuột trái.

  **1.8. dragStart**
  - Được gọi khi map bắt đầu được giữ và kéo chuột trái.

  **1.9. mouseMove**
  - Được gọi khi chuột di chuyển trên map.

  **1.10. mouseOut**
  - Được gọi khi chuột di chuyển ra ngoài map.

  **1.11. mouseOver**
  - Đưọc gọi khi chuột di chuyển từ ngoài vào trong map.

  **1.12. rightClick**
  - Được gọi khi click chuột phải trên map.

  **1.13. projectionChanged**
  - Được gọi khi các phép chiếu thay đổi.
  - Sẽ cập nhật ở phiên bản sau

  **1.14. tilesLoaded**
  - Được gọi khi tải tile hoàn thành.
  - Sẽ cập nhật ở phiên bản sau

  **1.15. markerClick**
  - Được gọi khi click chuột trái vào marker.

  **1.16. objectClick**
  - Được gọi khi click chuột trái vào các đối tượng (toà nhà, cây, cầu ...).

  **1.17. polygonClick**
  - Được gọi khi click chuột trái vào các đa giác.

  **1.18. polylineClick**
  - Được gọi khi click vào các chuỗi các đường thẳng.

  **1.19. circleClick**
  - Được gọi khi click vào hình tròn.

  **1.20. modeChanged**
  - Được gọi khi map thay đổi chế độ từ 2D sang 3D và ngược lại.

  **1.21. markerHover**
  - Được gọi khi di chuyển chuột vào marker.

  **1.22. objectHover**
  - Được gọi khi di chuyển chuột vào các đối tượng (toà nhà, cây, cầu ...)

  **1.23. polygonHover**
  - Được gọi khi di chuyển vào các đa giác.

  **1.24. polylineHover**
  - Được gọi khi di chuyển chuột vào các chuỗi đưởng thẳng.

  **1.25. circleHover**
  - Được gọi khi di chuyển chuột vào hình tròn.


  ---

## 2. Hướng dẫn chi tiết

  **-Cách đăng ký event chung-**
  ```javascript
    let event = map.addListener("event_name", (args) => {
    })
  ```

  **-Cách gỡ bỏ một event khi không sử dụng-**

  ```javascript
      event.remove()
  ```


  **2.1. cameraWillChange**
  ```javascript
    map.addListener("cameraWillChange", (args) => {
      console.log(args)
    })
  ```

  - **args**:
  ```javascript
    {camera: CameraPosition}
  ```
  - *camera: CameraPosition*

  - *gesture: boolean*
    - *true*:  camera bắt đầu thay đổi khi người dùng sử dụng các gesture.
    - *false*: camera bắt đầu thay đổi nhưng người dùng không sử dụng gesture.
  - **Kết quả**:

  ```javascript
    {camera: CameraPosition}
  ```

  **2.2. cameraChanging**
  ```javascript
    map.addListener("cameraChanging", (args) => {
      console.log(args)
    })
  ```

  - **args**:
  ```javascript
    { camera: CameraPosition}
  ```
  - *camera: CameraPosition*

  - **Kết quả**:

  ```javascript
    { camera: CameraPosition}
  ```

  **2.3. idle**
  ```javascript
    map.addListener("idle", (args) => {
      console.log(args)
    })
  ```

  - **args**:
  ```javascript
    { camera: CameraPosition}
  ```
  - *camera: CameraPosition*

  - **Kết quả**:

  ```javascript
    { camera: CameraPosition}
  ```

  **2.4. click**<br>
  **2.5. dblClick**<br>
  **2.6. drag**<br>
  **2.7. dragEnd**<br>
  **2.8. dragStart**<br>
  **2.9. mouseMove**<br>
  **2.10. mouseOut**<br>
  **2.11. mouseOver**<br>
  **2.12. rightClick**<br>

  - *Tất cả các sự kiện này đều có các tham số giống nhau*

  ```javascript
    map.addListener("click", (args) => {
      console.log(args)
    })
  ```

  ```javascript
    map.addListener("dblClick", (args) => {
      console.log(args)
    })
  ```

  ```javascript
    map.addListener("drag", (args) => {
      console.log(args)
    })
  ```

  ```javascript
    map.addListener("dragEnd", (args) => {
      console.log(args)
    })
  ```

  ```javascript
    map.addListener("dragStart", (args) => {
      console.log(args)
    })
  ```

  ```javascript
    map.addListener("mouseMove", (args) => {
      console.log(args)
    })
  ```

  ```javascript
    map.addListener("mouseOut", (args) => {
      console.log(args)
    })
  ```

  ```javascript
    map.addListener("mouseOver", (args) => {
      console.log(args)
    })
  ```

  ```javascript
    map.addListener("rightClick", (args) => {
      console.log(args)
    })
  ```

  - **args**:
  ```javascript
    { location: LatLng,
      point: Point,
      pixel: Point,
      xa: MouseEvent }
  ```
  - *location: LatLngn*

  - *point: Point*
    - Đơn vị point độc lập đối với mỗi màn hình.
  - *pixel: Point*
    - Pixel, px hay có khi gọi là pel (xuất phát từ “picture element”), chúng ta hay gọi là điểm ảnh, có dạng hình vuông.
  - *xa: MouseEvent*
  ```javascript
    {xa: MouseEvent}
  ```
  **- Kết quả**:<br>
  ```javascript
    { location: LatLng,
      point: Point,
      pixel: Point,
      xa: MouseEvent }
  ```
  **2.13. projectionChanged**

  - Đang cập nhật.

  **2.14. tilesLoaded**
  - Đang cập nhật.

  **2.15. markerClick**
  ```javascript
    map.addListener("markerClick", (args) => {
      console.log(args)
    })
  ```

  - **args**:
  ```javascript
    { marker: Marker,
      xa: MouseEvent }
  ```
  - *marker: Marker*

  - *xa: MouseEvent*
  ```javascript
    {xa: MouseEvent}
  ```
  **- Kết quả**:
  ```javascript
    { marker: Marker,
    xa: MouseEvent }
  ```

  **2.16. objectClick**
  ```javascript
    map.addListener("objectClick", (args) => {
      console.log(args)
    })
  ```

  - **args**:
  ```javascript
    {object: MapObject, xa: MouseEvent}
  ```
  - *object: MapObject*

  - *xa: MouseEvent*
  ```javascript
    {xa: MouseEvent}
  ```
  **- Kết quả**:
  ```javascript
    {object: MapObject, xa: MouseEvent}
  ```

  **2.17. polygonClick**
  ```javascript
    map.addListener("polygonClick", (args) => {
      console.log(args)
    })
  ```

  - **args**:
  ```javascript
    {polygon: Polygon, xa: MouseEvent}
  ```
  - *polygon: Polygon*

  - *xa: MouseEvent*
  ```javascript
    {xa: MouseEvent}
  ```
  **- Kết quả**:
  ```javascript
    {polygon: Polygon, xa: MouseEvent}
  ```

  **2.18. polylineClick**
  ```javascript
    map.addListener("polylineClick", (args) => {
      console.log(args)
    })
  ```

  - **args**:
  ```javascript
    {polyline: Polyline}
  ```
  - *polyline: Polyline*

  **- Kết quả**:
  ```javascript
    {polyline: Polyline}
  ```

  **2.19. circleClick**
  ```javascript
    map.addListener("circleClick", (args) => {
      console.log(args)
    })
  ```

  - **args**:
  ```javascript
    {circle: Circle}
  ```
  - *circle: Circle*

  **- Kết quả**:
  ```javascript
    {circle: Circle}
  ```

  **2.20. modeChanged**
  ```javascript
    map.addListener("modeChanged", (args) => {
      console.log(args)
    })
  ```

  - **args**:
  ```javascript
    {is3DMode: boolean}
  ```
  - *is3DMode: boolean*<br>
  **- true**:  *map chuyển từ chế độ 2D sang 3D*<br>
  **- false**: *map chuyển từ chế độ 3D sang 2D*<br>

  **- Kết quả**:
  ```javascript
    {is3DMode: boolean}
  ```

  **2.21. markerHover**
  ```javascript
    map.addListener("markerHover", (args) => {
      console.log(args)
    })
  ```

  - **args**:
  ```javascript
    { marker: Marker}
  ```
  - *marker: Marker*

  **- Kết quả**:
  *Kết quả dưới đây chỉ demo một event click*
  ```javascript
    { marker: Marker}
  ```

  **2.22. objectHover**
  ```javascript
    map.addListener("objectHover", (args) => {
      console.log(args)
    })
  ```

  - **args**:
  ```javascript
    {object: MapObject}
  ```
  - *object: MapObject*

  **- Kết quả**:
  ```javascript
    {object: MapObject}
  ```

  **2.23. polygonHover**
  ```javascript
    map.addListener("polygonHover", (args) => {
      console.log(args)
    })
  ```

  - **args**:
  ```javascript
    {polygon: Polygon}
  ```
  - *polygon: Polygon*


  **- Kết quả**:
  ```javascript
    {polygon: Polygon}
  ```

  **2.24. polylineHover**
  ```javascript
    map.addListener("polylineHover", (args) => {
      console.log(args)
    })
  ```

  - **args**:
  ```javascript
    {polyline: Polyline}
  ```
  - *polyline: Polyline*


  **- Kết quả**:
  ```javascript
    {polyline: Polyline}
  ```

  **2.25. circleHover**
  ```javascript
    map.addListener("circleHover", (args) => {
      console.log(args)
    })
  ```

  - **args**:
  ```javascript
    {circle: Circle}
  ```
  - *circle: Circle*

  **- Kết quả**:
  ```javascript
    {circle: Circle}
  ```


  License
  -------

  Copyright (C) 2016 IOT Link Ltd. All Rights Reserved.
