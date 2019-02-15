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
    objName?: string // Tên đối tượng lấy trên map (sẽ được cung cấp)
    objUrl?: string // Đường dẫn dữ liệu của đối tượng
    objData?: string // Nội dung dữ liệu của đối tượng
    textureUrl?: string // Đường texture của đối tượng
    textureData?: string // Nội dung dữ liệu texture
    textureName?: string // Tên của texture trên map (sẽ được cung cấp)
  }

  Chú ý: thứ tự ưu tiên cài đặt dữ liệu và texture cho đối tượng.
  (Object hoặc Texture): URL->DATA->NAME.
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
    setObjUrl(url: string): void // Cài đặt đường dẫn lấy thông tin vẽ đối tượng
    setTextureUrl(url: string): void // Cài đặt đường dẫn texture của đối tượng
    setObjData(data: string): void // Cài đặt dữ liệu cho đối tượng
    setTextureData(imageBase64: string): void // Cài đặt dữ liệu texture của đối tượng
    setObjName(nameObj: string): void // Cài đặt tên đối tượng
    setTextureName(textureName: string): void // Cài đặt tên cho texture.
    setMap(map: Map): void // Cài đặt map cần vẽ đối tượng.
  }

```

## 2. Tạo đối tượng

```javascript
  //tạo đối tượng MapObject từ MapObjectOptions
  let mapObject = new map4d.MapObject({
      id: "dungtest",
      location: {lat: 10.793113, lng:106.720739},
      objName: "58a2b79436eace2398d47c01",
      textureName: "CauKhanhHoi.png"
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
