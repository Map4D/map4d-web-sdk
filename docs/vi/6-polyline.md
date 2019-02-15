# Polyline
Lớp Polyline cho phép người dùng vẽ một polyline lên map.

## 1. Polyline & PolylineOptions

```javascript
  interface PolylineOptions {
    path: ILatLng[] // Một mảng danh sách các toạ độ cần vẽ polyline lên map.
    strokeWidth?: number // Chiều rộng polyline
    strokeColor?: string // Màu sắc
    strokeOpacity?: number // Độ trong suốt
    visible?: boolean // Ẩn hoặc hiện polyline
    closed?: boolean // Cho phép nối điểm đầu và điểm cuối lại với nhau.
  }

  class Polyline {
    constructor(options: PolylineOptions) // Khởi tạo polyline với PolylineOptions
    getPath(): LatLng[] // Lấy thông tin danh sách cách toạ độ cần vẽ polyline
    getMap(): Map // Lấy thông tin map.
    setMap(map: Map): void // Cài đặt map cần vẽ.
    setPath(path: ILatLng[]): void // Cài đặt danh sách các toạ độ cần vẽ.
    setStrokeWidth(strokeWidth: number): void // Cài đặt chiều rộng polyline.
    setClosed(closed: boolean): void // Cho phép nối điểm đầu và điểm cuối.
    setStrokeColor(strokeColor: string): void // Cài đặt màu sắc polyline.
    setStrokeOpacity(strokeOpacity: number): void // Cài đặt độ trong suốt cho polyline.
    setVisible(visible: boolean): void // Cài đặt ẩn hiện polyline.
    getStrokeWidth(): number // Lấy chiều rộng polyline
    getStrokeColor(): string // Lấy màu sắc polyline.
    getStrokeOpacity(): number // Lấy độ trong suốt polyline
    isVisible(): boolean // Kiểm tra ẩn hiện polyline
    isClosed(): boolean // Kiểm tra điểm đầu và điểm cuối có nối lại với nhau không ?
  }
```


## 2. Tạo polyline

```javascript
  //tạo đối tượng polyline từ PolylineOptions
  let polyline = new map4d.Polyline({
        path: [
          [10.772431, 106.699380],
          [10.773201, 106.700147],
          [10.771783, 106.700763],
          [10.772302, 106.701901],
          [10.773267, 106.701493],
          [10.773599, 106.702835]
        ], visible: true, strokeColor: "#ff0000", strokeWidth: 10, strokeOpacity: 1.0,
        closed: true
      })
  //thêm marker vào map    
  polyline.setMap(map)
```

## 3. Sự kiện click polyline

Phát sinh khi người dùng click vào polyline

```javascript
let clickMapsEventClick = this.map.addListener("polylineClick", (args) => {
      console.log("Polyline clicked: ")
      console.log(args)
    })

    //sau khi dùng xong
    clickMapsEventClick.remove();
```

## 4. Sự kiện hover polyline

Phát sinh khi người dùng hover vào polyline

```javascript
  let clickMapsEventClick = this.map.addListener("polylineHover", (arg) => {
      console.log("Object hover: ")
      console.log(arg)
    })

    //sau khi dùng xong
    clickMapsEventClick.remove();
```

License
-------

Copyright (C) 2016 IOT Link Ltd. All Rights Reserved.
