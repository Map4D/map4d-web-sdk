# Type Public Map4D-SDK

```javascript
  // Type definitions for map4dsdk 1.0
  // Project: https://github.com/iotlinkadmin/map4d-web-sdk (Does not have to be to GitHub, but prefer linking to a source code repository rather than to a project website.)
  // Definitions by: Sua Le <https://github.com/sua8051>
  // Definitions: https://github.com/DefinitelyTyped/DefinitelyTyped

  declare module 'map4d' {
    interface CircleOptions {
      center: ILatLng
      radius?: number
      fillColor?: string
      fillOpacity?: number
      visible?: boolean
    }

    interface MapObjectOptions {
      id: string
      location?: ILatLng
      name?: string
      scale?: number
      bearing?: number
      elevation?: number
      heightScale?: number
      objUrl?: string
      textureUrl?: string
      objData?: string
      textureData?: string
      objName?: string
      textureName?: string
    }

    class Circle {
      constructor(options: CircleOptions)
      getMap(): Map
      setMap(map: Map): void
      setCenter(center: ILatLng): void
      setRadius(radius: number): void
      setFillColor(fillColor: string)
      setFillOpacity(fillOpacity: number)
      setVisible(visible: boolean)
      getCenter(): LatLng
      getRadius(): number
      getFillColor(): string
      getFillOpacity(): number
      isVisible(): boolean
    }

    type ICameraPosition  = CameraPosition | {target?: ILatLng, tilt?: number, bearing?: number, zoom?: number}
    class CameraPosition{
      setTarget(target: ILatLng): void
      setTilt(degrees: number): void
      setBearing(degrees: number): void
      setZoom(zoom: number)
      getTarget(): LatLng
      getTilt(): number
      getBearing(): number
      getZoom(): number
    }

    class MapObject {
      constructor(options?: MapObjectOptions)
      setId(id: string): void
      getId(): string
      getName(): string
      getPlaces() : string[]
      getScale(): any
      getBearing(): number
      getLocation(): LatLng
      getElevation(): number
      getHeightScale(): number
      getCamera(): CameraPosition
      getTypes(): string[]
      isVerified(): boolean
      getMinZoom(): number
      getMaxZoom(): number
      getStartDate(): number
      getEndDate(): number
      setObjUrl(url: string): void
      setTextureUrl(url: string): void
      setObjData(data: string): void
      setTextureData(imageBase64: string): void
      setObjName(nameObj: string): void
      setTextureName(textureName: string): void
      setMap(map: Map): void
    }

    export class Icon {
      constructor(width: number, height: number, url: string)
      clone(): Icon
      getWidth(): number
      getHeight(): number
      getUrl(): string
    }

    type ILatLng  = LatLng | {lat: number, lng: number} | [number, number]
    class LatLng {
      constructor(lat: number, lng: number)
      equals(other: LatLng): boolean
      lat(): number
      lng(): number
      toString(): string
      normalize(): LatLng
    }

    type ILatLngBounds = LatLngBounds | [ILatLng, ILatLng] | [number, number, number, number]
    class LatLngBounds {
      constructor(sw: ILatLng, ne: ILatLng)
      getCenter(): LatLng
      getNortheast(): LatLng
      getSouthwest(): LatLng
      extend(point: ILatLng): LatLngBounds
    }

    enum MapEvent {
      cameraWillChange = 0,
      cameraChanging,
      idle,
      click,
      dblClick,
      drag,
      dragEnd,
      dragStart,
      mouseMove,
      mouseOut,
      mouseOver,
      projectionChanged,
      rightClick,
      tilesLoaded,
      markerClick,
      objectClick,
      polygonClick,
      polylineClick,
      circleClick,
      modeChanged,
      markerHover,
      objectHover,
      polygonHover,
      polylineHover,
      circleHover
    }

    enum ControlOptions {
      TOP_LEFT,
      TOP_RIGHT,
      BOTTOM_LEFT,
      BOTTOM_RIGHT
    }

    enum SwitchMode {
      Auto2DTo3D,
      Auto3DTo2D,
      Auto,
      Manual
    }

    export enum Weather {
      Rain = 0,
      Snow,
      Sun
    }

    export enum TimeEffect{
      Live,
      Morning,
      Noon,
      AfterNoon,
      Evening
    }

    interface MapOptions {
      center?: [number, number]
      zoom?: number
      minZoom?: number
      maxZoom?: number
      geolocate?: boolean
      accessKey?: string
      tilt?: number,
      bearing?: number,
      mapControls?: boolean
      mapControlOptions?: ControlOptions
    }

    interface AnimationOptions {
      duration?: number
      easing?: (arg0: number) => number
      animate?: boolean
    }

    interface PaddingOptions {
      top?: number
      bottom?: number
      left?: number
      right?: number
    }

    class Map {
      constructor(container: HTMLElement, options?: MapOptions)
      enable3dMode(enabled: boolean): void
      getCamera(): CameraPosition
      setCamera(position: ICameraPosition): void
      getBounds(): LatLngBounds
      setMapUrl(mapUrl: string, _3dMode: boolean): void
      getMapUrl(): string
      setMinZoom(minZoom: number): void
      setMaxZoom(maxZoom: number): void
      setWeather(weather: Weather): void
      getWeather(): Weather
      panBy(offset: IPoint, animationOptions?: AnimationOptions): void
      panTo(latLng: ILatLng, animationOptions?: AnimationOptions): void
      flyTo(latLng: ILatLng, zoom: number, animationOptions?: AnimationOptions): void
      flyToMyLocation(animate: boolean): void
      fitBounds(bounds: ILatLngBounds, padding?: PaddingOptions, animationOptions?: AnimationOptions): void
      setSwitchMode(mode: SwitchMode): void
      addListener(event: string | MapEvent, func: Function): MapsEventListener
      setTime(date: Date): void
      setInfoWindow(infoWindow: (marker: Marker) => string | Node): void
      setInfoContents(infoContents: (marker: Marker) => string | Node): void
      is3DMode(): boolean
      getMinZoom(): number
      getPreferMinZoom(): number
      getMaxZoom(): number
      getMaxNativeZoom(): number
      getTimeEffect(): number
      setTimeEffect(timeEffect : TimeEffect): void
    }

    interface MapsEventListener {
      remove(): void
    }

    interface MarkerOptions {
      position: ILatLng
      visible?: boolean
      anchor?: IPoint
      icon?: Icon | string
      elevation?: number
      title?: string
      snippet?: string
      windowAnchor?: IPoint
    }

    class Marker {
      constructor(options: MarkerOptions)
      setMap(map: Map)
      setPosition(position: ILatLng)
      setVisible(visible: boolean)
      setAnchor(anchor: IPoint)
      setIcon(icon: Icon | string)
      setElevation(elevation: number)
      getPosition(): LatLng
      isVisible(): boolean
      getAnchor(): Point
      getIcon(): Icon | string
      getElevation(): number
      getMap(): Map
      hideInfoWindow(): void
      showInfoWindow(): void
      getTitle(): string
      setTitle(title: string): void
      getSnippet(): string
      setSnippet(snippet: string): void
      setWindowAnchor(anchor: IPoint): void
      isInfoWindowShown(): boolean
    }

    type IPoint  = Point | {x: number, y: number} | [number, number]
    class Point {
      x: number
      y: number
      constructor(x: number, y: number)
      equals(other: Point): boolean
      toString(): string
    }

    interface PolygonOptions {
      paths: ILatLng[][]
      fillColor?: string
      fillOpacity?: number
      visible?: boolean
    }

    class Polygon {
      constructor(options: PolygonOptions)
      getMap(): Map
      setMap(map: Map): void
      setPaths(paths: ILatLng[][]): void
      setFillColor(fillColor: string): void
      setFillOpacity(fillOpacity: number): void
      setVisible(visible: boolean): void
      getPaths(): LatLng[][]
      getFillColor(): string
      getFillOpacity(): number
      isVisible(): boolean
    }

    interface PolylineOptions {
      path: ILatLng[]
      strokeWidth?: number
      strokeColor?: string
      strokeOpacity?: number
      visible?: boolean
      closed?: boolean
    }

    class Polyline {
      constructor(options: PolylineOptions)
      getPath(): LatLng[]
      getMap(): Map
      setMap(map: Map): void
      setPath(path: ILatLng[]): void
      setStrokeWidth(strokeWidth: number): void
      setClosed(closed: boolean): void
      setStrokeColor(strokeColor: string): void
      setStrokeOpacity(strokeOpacity: number): void
      setVisible(visible: boolean): void
      getStrokeWidth(): number
      getStrokeColor(): string
      getStrokeOpacity(): number
      isVisible(): boolean
      isClosed(): boolean
    }

    class Projection {
      constructor(map: Map)
      fromLatLngToScreen(latLng: LatLng): Point
      fromScreenToLatLng(screenCoordinate: IPoint): LatLng
    }

    type TileAreaId = number
    interface TileAreaOptions {
      bounds: ILatLngBounds
      url?: string
      minZoom?: number
      maxZoom?: number
    }

    class TileArea {
      constructor(options: TileAreaOptions)
      getBounds(): LatLngBounds
      getUrl(): string
      getMinZoom(): number
      getMaxZoom(): number
      getMap(): Map
      setMap(map: Map): void
      setBounds(bounds: ILatLngBounds): void
      setMinZoom(minZoom: number): void
      setMaxZoom(maxZoom: number): void
      setUrl(url: string): void
    }
  }
```
