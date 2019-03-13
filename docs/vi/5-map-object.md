# MapObject
Lớp MapObject cho phép người dùng thao tác với các đối tượng trên map như toà nhà, cây xanh, cầu...<br>
Có thể thêm một đối tượng lên map hoặc đọc thông tin đối tượng từ map.

## 1. MapObject & MapObjectOptions

```javascript
interface MapObjectOptions {
    id: string // id của đối tượng, nếu id = null hoặc trùng với id đã có sẵn thì sẽ phát sinh lỗi.
    location?: ILatLng // Vị trí đặt đối tượng lên map.
    name?: string // Tên của đối tượng
    scale?: number // Tỉ lệ vẽ của đối tượng
    bearing?: number // Góc quay của đối tượng
    elevation?: number // Độ cao so với mặt nước biển
    heightScale?: number // Tỉ lệ vẽ chiều cao của đối tượng
    obj?: string // Tên đối tượng trên map(sẽ được cung cấp), đường dẫn hoặc nội dung dữ liệu đối tượng
    texture?: string // Tên của texture trên map(sẽ được cung cấp), đường dẫn hoặc nội dung dữ liệu texture
  }

  Chú ý: Cài đặt tên, đường dẫn hoặc nội dung dữ liệu cho đối tượng hoặc texture.
  Chỉ cần cài đặt 1 trong 3 thuộc tính trên là được.

  class MapObject {
    constructor(options?: MapObjectOptions) // Tạo đối tượng từ MapObjectOptions
    setId(id: string): void // Cài đặt thông tin ID của đối tượng
    getId(): string // Lấy thông tin ID của đối tượng
    getName(): string // Lấy thông tin tên của đối tượng
    getPlaces() : string[] // Lấy thông tin
    getScale(): any // Lấy thông tin tỉ lệ vẽ của đối tượng
    getBearing(): number // Lấy góc quay của đối tượng
    getLocation(): LatLng // Lấy thông tin vị trí đặt đối tượng
    getElevation(): number // Lấy thông tin độ cao của đối tượng
    getHeightScale(): number // Lấy thông tin tỉ lệ vẽ chiều cao của đối tượng
    getCamera(): CameraPosition // Lấy thông tin camera của đối tượng
    getTypes(): string[] // Lấy thông tin kiểu đối tượng
    isVerified(): boolean //
    getMinZoom(): number // Lấy thông tin mức zoom tối thiểu
    getMaxZoom(): number // Lấy thông tin mức zoom tối
    getStartDate(): number // Lấy thông tin ngày bắt đầu xây dựng đối tượng
    getEndDate(): number // Lấy thông tin ngày kết thúc đối tượng (ngày phá bỏ ...), khi đó sẽ không xuất hiện trên bản đồ.
    setObj(obj: string): void // Cài đặt tên đối tượng trên map(sẽ được cung cấp), đường dẫn hoặc nội dung dữ liệu đối tượng
    setTexture(texture: string): void // Cài đặt tên của texture trên map(sẽ được cung cấp), đường dẫn hoặc nội dung dữ liệu texture
    setLocation(location: ILatLng): void // Cài đặt vị trí đặt đối tượng lên map.
    setElevation(Elevation: number): void // Cài đặt độ cao so với mặt nước biển
    setBearing(bearing: number): void // Cài đặt góc quay của đối tượng
    setName(name: string): void // Cài đặt tên của đối tượng
  }

```

## 2. Tạo đối tượng

```javascript
  //tạo đối tượng MapObject từ MapObjectOptions
  let mapObject = new map4d.MapObject({
      id: "dungtest",
      location: {lat: 10.793113, lng:106.720739},
      obj: "58a2b79436eace2398d47c01",
      texture: "CauKhanhHoi.png"
    })
    // set Map
    this.mapObject.setMap(map)
```

## 3. Sự kiện click vào đối tượng

Phát sinh khi người dùng click vào đối tượng trên map.

```javascript
let clickMapsEventClick = this.map.addListener("objectClick", (args) => {
      console.log("Object clicked: ")
      console.log(args)
    })

    //sau khi dùng xong
    clickMapsEventClick.remove();
```

## 4. Sự kiện hover object

Phát sinh khi người dùng hover vào đối tượng trên map

```javascript
let clickMapsEventClick = this.map.addListener("objectHover", (arg) => {
      console.log("Object hover: ")
      console.log(arg)
    })

    //sau khi dùng xong
    clickMapsEventClick.remove();
```

License
-------

Copyright (C) 2016 IOT Link Ltd. All Rights Reserved.
