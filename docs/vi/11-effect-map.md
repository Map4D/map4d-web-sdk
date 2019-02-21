# Cài đặt Hiệu Ứng Map4D-SDK

## 1. Cài đặt hiệu ứng thời tiết
Map4D SDK cho phép người dùng cài đặt các hiệu ứng theo thời gian thực hoặc thủ công

```javascript
setWeather(weather: Weather): void
getWeather(): Weather
```

```javascript
map.setWeather(Weather.Rain)
this.map.getWeather()
```
- **setWeather**: Cài đặt hiệu ứng thời tiết
  - *Weather.Rainy* : Hiệu ứng thời tiết trời đang mưa
  - *Weather.Snowy* : Hiệu ứng thời tiết tuyết đang rơi
  - *Weather.Sunny* : Hiệu ứng thời tiết trời nắng
  - *Weather.Live*  : Hiệu ứng thời tiết tự động cập nhật theo thời gian thực bằng hệ thống cảm biến đã có ở một số nơi.

- **getWeather**: Trả về thông tin thời tiết hiện tại


## 2. Cài đặt hiệu ứng theo thời gian
Map4D SDK cho phép người dùng cài đặt hiệu ứng trên map theo thời gian, hiện tại Map4D đã hỗ trợ hiệu ứng buổi sáng, trưa, chiều, tối và theo thời gian thực.
```javascript
setTimeEffect(timeEffect : TimeEffect): void
getTimeEffect(): number
```

```javascript
map.setTimeEffect(map4d.TimeEffect.Morning)
map.getTimeEffect()
```

- **setTimeEffect**: Cài đặt hiệu ứng thời gian trên map
  - *TimeEffect.Live* : Hiệu ứng theo thời gian thực.
  - *TimeEffect.Morning* : Hiệu ứng thời gian buổi sáng
  - *TimeEffect.Noon* : Hiệu ứng thời gian buổi trưa
  - *TimeEffect.AfterNoon*  : Hiệu ứng thời gian buổi chiều
  - *TimeEffect.Evening*  : Hiệu ứng thời gian buổi tối

- **getTimeEffect**: Trả về thông tin thời gian hiện tại

## 3. Cài đặt hiệu ứng bóng đổ
Map4D SDK cho phép người dùng cài đặt hiệu ứng bóng đổ trên map.
```javascript
setShadowEffect(enabled: boolean): void
```

```javascript
map.setShadowEffect(true)
```

- **setShadowEffect**: Cài đặt hiệu ứng bóng đổ trên map
  - *true* : Cho phép cài đặt hiệu ứng bóng đổ.
  - *false* : Không cho phép cài đặt hiệu ứng bóng đổ.

## 4. Cài đặt hiệu ứng mặt nước
Map4D SDK cho phép người dùng cài đặt hiệu ứng mặt nước trên map.
```javascript
setWaterEffect(enabled: boolean): void
```

```javascript
map.setWaterEffect(true)
```

- **setWaterEffect**: Cài đặt hiệu ứng mặt nước trên map
  - *true* : Cho phép cài đặt hiệu ứng mặt nước.
  - *false* : Không cho phép cài đặt hiệu ứng mặt nước.


License
-------

Copyright (C) 2016 IOT Link Ltd. All Rights Reserved.
