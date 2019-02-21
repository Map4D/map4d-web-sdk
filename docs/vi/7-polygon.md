# Polygon
Lớp Polygon cho phép người dùng vẽ một Polygon lên map.

## 1. Polygon & PolygoneOptions

```javascript
  interface PolygonOptions {
    paths: ILatLng[][] // Danh sách các toạ độ cần vẽ
    fillColor?: string // Màu sắc polygon
    fillOpacity?: number // Độ trong suốt polygon
    visible?: boolean // Ẩn hoặc hiện polygon
  }

  class Polygon {
    constructor(options: PolygonOptions) // Khỏi tạo polygon bằng PolygonOptions
    getMap(): Map // Lấy thông tin map
    setMap(map: Map): void // Cài đặt map cần vẽ polygon
    setPaths(paths: ILatLng[][]): void // Cài đặt danh sách các toạ độ cần vẽ polygon
    setFillColor(fillColor: string): void // Cài đặt màu sắc polygon
    setFillOpacity(fillOpacity: number): void // Cài đặt độ trong suốt polygon
    setVisible(visible: boolean): void // Cài đặt ẩn hiện polygon
    getPaths(): LatLng[][] // Lấy danh sách các toạ độ cần vẽ polygon
    getFillColor(): string // Lấy thông tin màu sắc
    getFillOpacity(): number // Lấy thông tin độ trong suốt
    isVisible(): boolean // Kiểm tra polygon ẩn hiện
  }
```


## 2. Tạo polygon

```javascript
  //tạo đối tượng polygon từ PolygonOptions
  let polygonOption: map4d.PolygonOptions = {
      paths:
        [[{lat: 10.773201, lng: 106.700147}, {lat: 10.771783, lng: 106.700763},
          {lat: 10.772302, lng: 106.701901}, {lat: 10.773267, lng: 106.701493},
          {lat: 10.773201, lng: 106.700147}],
          // hole1
          [{lat: 10.772785, lng: 106.700738}, {lat: 10.772904, lng: 106.701304},
            {lat: 10.772752, lng: 106.701319}, {lat: 10.772650, lng: 106.700651},
            {lat: 10.772785, lng: 106.700738}],
          // hole2
          [{lat: 10.772356, lng: 106.700802}, {lat: 10.772479, lng: 106.701413},
            {lat: 10.772285, lng: 106.701497}, {lat: 10.772059, lng: 106.701064},
            {lat: 10.772356, lng: 106.700802}]], fillOpacity: 0.9
    }
  //thêm polygon vào map    
  let polygon = new map4d.Polygon(polygonOption)
    polygon.setMap(this.map)
```

  ***Chú ý:***
  -  Điểm đầu điểm cuối danh sách các điểm cần vẽ phải giống nhau
  -  Xem demo ở ví dụ trên
  ```javascript
      [ {lat: 10.773201, lng: 106.700147},
        {lat: 10.771783, lng: 106.700763},
        {lat: 10.772302, lng: 106.701901},
        {lat: 10.773267, lng: 106.701493},
        {lat: 10.773201, lng: 106.700147}]
  ```

## 3. Sự kiện click polygon

Phát sinh khi người dùng click vào polygon

```javascript
let clickMapsEventClick = this.map.addListener("polygonClick", (args) => {
      console.log("polygon clicked: ")
      console.log(args)
    })

    //sau khi dùng xong
    clickMapsEventClick.remove();
```

## 4. Sự kiện hover polygon

Phát sinh khi người dùng hover vào polygon

```javascript
  let clickMapsEventClick = this.map.addListener("polygonHover", (arg) => {
      console.log("Polygon hover: ")
      console.log(arg)
    })

    //sau khi dùng xong
    clickMapsEventClick.remove();
```

License
-------

Copyright (C) 2016 IOT Link Ltd. All Rights Reserved.
