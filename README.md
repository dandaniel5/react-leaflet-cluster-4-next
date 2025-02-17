# react-leaflet-cluster-4-next ([github-repo](https://github.com/dandaniel5/react-leaflet-cluster-4-next)

This is a fork of [react-leaflet-cluster](https://www.npmjs.com/package/react-leaflet-cluster), originally created by [akursat](https://github.com/akursat/react-leaflet-cluster).  
It includes slight modifications to fix issues related to CSS imports in Next.js.


## Key Changes
- Disabled CSS imports from `index.js`.
- **Required:** Add `MarkerCluster.css` and `MarkerCluster.Default.css` manually to your global CSS.

## Compatibility
- Tested with **React 18** and **Next.js 14.2**.
- Use with `@react-leaflet/core@2.1.0`.

## Installation

```bash
npm install react-leaflet-cluster-4-next
```
## example
```
import MarkerClusterGroup from 'react-leaflet-cluster-4-next';
...

<MapContainer
      ref={mapRef}
      zoomControl={false}
      center={defaltLoc}
      className="w-screen h-screen z-0"
    >
...
      <MarkerClusterGroup
        chunkedLoading
      >
        {markers?.map((marker, index) => (
          <CustomMarker key={index} marker={marker} index={index} />
        ))}
      </MarkerClusterGroup>
    </MapContainer >

```
## css to global
```
//MarkerCluster.css 

.leaflet-cluster-anim .leaflet-marker-icon, .leaflet-cluster-anim .leaflet-marker-shadow {
	-webkit-transition: -webkit-transform 0.3s ease-out, opacity 0.3s ease-in;
	-moz-transition: -moz-transform 0.3s ease-out, opacity 0.3s ease-in;
	-o-transition: -o-transform 0.3s ease-out, opacity 0.3s ease-in;
	transition: transform 0.3s ease-out, opacity 0.3s ease-in;
}

.leaflet-cluster-spider-leg {
	/* stroke-dashoffset (duration and function) should match with leaflet-marker-icon transform in order to track it exactly */
	-webkit-transition: -webkit-stroke-dashoffset 0.3s ease-out, -webkit-stroke-opacity 0.3s ease-in;
	-moz-transition: -moz-stroke-dashoffset 0.3s ease-out, -moz-stroke-opacity 0.3s ease-in;
	-o-transition: -o-stroke-dashoffset 0.3s ease-out, -o-stroke-opacity 0.3s ease-in;
	transition: stroke-dashoffset 0.3s ease-out, stroke-opacity 0.3s ease-in;
}

// MarkerCluster.Default.css

.marker-cluster-small {
	background-color: rgba(181, 226, 140, 0.6);
	}
.marker-cluster-small div {
	background-color: rgba(110, 204, 57, 0.6);
	}

.marker-cluster-medium {
	background-color: rgba(241, 211, 87, 0.6);
	}
.marker-cluster-medium div {
	background-color: rgba(240, 194, 12, 0.6);
	}

.marker-cluster-large {
	background-color: rgba(253, 156, 115, 0.6);
	}
.marker-cluster-large div {
	background-color: rgba(241, 128, 23, 0.6);
	}

	/* IE 6-8 fallback colors */
.leaflet-oldie .marker-cluster-small {
	background-color: rgb(181, 226, 140);
	}
.leaflet-oldie .marker-cluster-small div {
	background-color: rgb(110, 204, 57);
	}

.leaflet-oldie .marker-cluster-medium {
	background-color: rgb(241, 211, 87);
	}
.leaflet-oldie .marker-cluster-medium div {
	background-color: rgb(240, 194, 12);
	}

.leaflet-oldie .marker-cluster-large {
	background-color: rgb(253, 156, 115);
	}
.leaflet-oldie .marker-cluster-large div {
	background-color: rgb(241, 128, 23);
}

.marker-cluster {
	background-clip: padding-box;
	border-radius: 20px;
	}
.marker-cluster div {
	width: 30px;
	height: 30px;
	margin-left: 5px;
	margin-top: 5px;

	text-align: center;
	border-radius: 15px;
	font: 12px "Helvetica Neue", Arial, Helvetica, sans-serif;
	}
.marker-cluster span {
	line-height: 30px;
	}
```
