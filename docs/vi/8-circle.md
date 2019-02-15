# Circle
Lớp Circle cho phép người dùng vẽ một Circle lên map.

## 1. Circle & CircleOptions

```javascript
  interface CircleOptions {
    center: ILatLng // Tâm của Circle
    radius?: number // Bán kính Circle (Đơn vị: m)
    fillColor?: string // Màu sắc Circle
    fillOpacity?: number // Độ trong suốt Circle
    visible?: boolean // Ẩn hoặc hiện Circle
  }

  class Circle {
    constructor(options: CircleOptions) // Khởi tạo Circle bằng CircleOptions
    getMap(): Map // Lấy thông tin map
    setMap(map: Map): void // Cài đặt map cần vẽ Circle
    setCenter(center: ILatLng): void // Cài đặt tâm Circle
    setRadius(radius: number): void // Cài đặt bán kính Circle
    setFillColor(fillColor: string) // Cài đặt màu sắc Circle
    setFillOpacity(fillOpacity: number) // Cài đặt độ trong suốt Circle
    setVisible(visible: boolean) // Cài đặt ẩn hiện Circle
    getCenter(): LatLng // Lấy thông tin tâm Circle
    getRadius(): number // Lấy thông tin bán kính Circle
    getFillColor(): string // Lấy thông tin màu sắc Circle
    getFillOpacity(): number // Lấy thông tin độ trong suốt Circle
    isVisible(): boolean // Kiểm tra ẩn hiện Circle
  }
```


## 2. Tạo circle

```javascript
  //tạo đối tượng circle từ CircleOptions
  let circle = new map4d.Circle({center: {lat: 10.773201, lng: 106.700147}, radius: 100})

  //thêm circle vào map    
  circle.setMap(this.map)
```

## 3. Sự kiện click circle

Phát sinh khi người dùng click vào polygon

```javascript
let clickMapsEventClick = this.map.addListener("circleClick", (args) => {
      console.log("CircleClick clicked: ")
      console.log(args)
    })

    //sau khi dùng xong
    clickMapsEventClick.remove();
```

## 4. Sự kiện hover Circle

Phát sinh khi người dùng hover vào circle

```javascript
  let clickMapsEventClick = this.map.addListener("circleHover", (arg) => {
      console.log("Circle hover: ")
      console.log(arg)
    })

    //sau khi dùng xong
    clickMapsEventClick.remove();
```

License
-------

Copyright (C) 2016 IOT Link Ltd. All Rights Reserved.
