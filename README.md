# react-google-layer-leaflet

<!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->
[![All Contributors](https://img.shields.io/badge/all_contributors-1-orange.svg?style=flat-square)](#contributors-)
<!-- ALL-CONTRIBUTORS-BADGE:END -->

A React component to implement Google Map tile layers on a Leaflet map.
And a helper utility to lazily load the Google Maps Api.

**NB: This package is not ready for use**

## Installation

Using yarn

```bash
yarn add react-google-layer-leaflet
```

or with NPM

```bash
 npm install react-google-layer-leaflet 
```

## Motivation

There are a number of options for adding a google maps layer to leaflet. However most of them are un-maintained and no longer compatible with `react-leaflet` v3.x. If you want you could use [react-leaflet-google-layer](https://www.npmjs.com/package/react-leaflet-google-layer). `react-google-layer-leaflet` does two things differently and its really preference which should decide between the two. 1. Completely decoupling how the `Google Maps JS API` is loaded. 2. Being a simple wrapper for [L.GridLayer.GoogleMutant](https://gitlab.com/IvanSanchez/Leaflet.GridLayer.GoogleMutant) and nothing else.

## Basic Usage

```javascript
import React, { useEffect } from 'react'
import { MapContainer } from 'react-leaflet'
import GoogleLayer, { googleMapsApiLoader } from 'react-google-layer-leaflet'

const position = [51.505, -0.09]

function MyMap(){

useEffect(() => {
  // call this anytime after app start up. 
  googleMapsApiLoader({
    apiKey: 'YOUR_API_KEY,
    version: '3.43', // of the api to use. 3.43 was the latest at time of writing 
    id: 'google-maps-api', // ensures calling it multiple times will not load multiple script tags
  })
},[])


return (
  <MapContainer center={position} zoom={13} >
    <GoogleLayer type="satellite" />

    <Marker position={position}>
      <Popup>
        A pretty CSS3 popup. <br /> Easily customizable.
      </Popup>
    </Marker>
  </MapContainer>
)
}
```

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
    <td align="center"><a href="http://www.seanrennie.com"><img src="https://avatars.githubusercontent.com/u/32762874?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Sean Rennie</b></sub></a><br /><a href="https://github.com/Rennzie/react-leaflet-google/commits?author=Rennzie" title="Code">💻</a></td>
  </tr>
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!
