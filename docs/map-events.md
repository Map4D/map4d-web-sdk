# Map events

Map4D Web SDK cung cấp các sự kiện của map hay tương tác của người dùng giúp cho nhà phát triển có thể lắng nghe và xử lý

- cameraWillChange: Được gọi khi một trong các thông số camera (tâm, góc nghiêng, góc quay, mức zoom) của map chuẩn bị thay đổi.
- cameraChanging: Được gọi khi một trong các thông số camera (tâm, góc nghiêng, góc quay, mức zoom) của map đang thay đổi.
- idle: Được gọi khi các thông số camera (tâm, góc nghiêng, góc quay, mức zoom) của map kết thúc sự thay đổi.
- hover: Được gọi khi rê chuột vào annotation hoặc đối tượng 3D.
- click: Được gọi khi có sự kiện click trên map, annotation hoặc đối tượng 3D.
- dblClick: Được gọi khi click 2 lần chuột trái vào map, annotation hoặc đối tượng 3D.
- drag: Được gọi khi map đang được giữ và kéo chuột trái.
- dragStart: Được gọi khi map bắt đầu được giữ và kéo chuột trái.
- dragEnd: Được gọi khi map kết thúc giữ và kéo chuột trái.
- mouseMove: Được gọi khi chuột di chuyển trên map.
- mouseOut: Được gọi khi chuột di chuyển ra ngoài map.
- mouseOver: Đưọc gọi khi chuột di chuyển từ ngoài vào trong map.
- projectionChanged
- rightClick: Được gọi khi click chuột phải trên map, annotation hoặc đối tượng 3D.
- tilesLoaded: Được gọi khi tất cả các visible tiles đã load hoàn thành (visible tiles là tất cả tiles sẽ được hiển thị trên màn hình)
- modeChanged: Được gọi khi map chuyển từ 2D sang 3D và ngược lại
- longClick: Được gọi khi giữ chuột trái trong 1 khoảng thời gian trên bản đồ
- boundsChanged: Được gọi khi viewport đã thay đổi

## 