<script>
/* global mapboxgl */
export default {
  mounted: function () {
    this.mapThing();
  },
  methods: {
    mapThing: function () {
      mapboxgl.accessToken = process.env.VUE_APP_API_KEY;
      const map = new mapboxgl.Map({
        container: "map", // container ID
        style: "mapbox://styles/mapbox/streets-v11", // style URL
        center: [-74.5, 40], // starting position [lng, lat]
        zoom: 5, // starting zoom
        projection: "globe", // display the map as a 3D globe
      });

      map.on("style.load", () => {
        map.setFog({}); // Set the default atmosphere style

        // create the popup
        const popup = new mapboxgl.Popup({ offset: 25 }).setText("Pretty cool");

        const el = document.createElement("div");
        el.id = "marker";

        // Create a default Marker and add it to the map.
        const marker1 = new mapboxgl.Marker(el).setLngLat([-66.12421, 18.47103]).setPopup(popup).addTo(map);
        console.log(marker1);
      });
    },
  },
};
</script>

<template>
  <div class="about">
    <h1>This is an about page</h1>
  </div>
  <div id="map"></div>
</template>

<style>
body {
  margin: 0;
  padding: 0;
}
#map {
  position: absolute;
  top: 0;
  bottom: 0;
  width: 100%;
}
#marker {
  background-image: url("https://www.worldatlas.com/r/w1200/upload/00/e1/11/shutterstock-1704281335.jpg");
  background-size: cover;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  cursor: pointer;
}

.mapboxgl-popup {
  max-width: 200px;
}
</style>
