<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import Darkmode from "darkmode-js";
// import Legra from "legra";
// import Moveable from "moveable";

export default {
  name: "HomeView",
  components: {
    HelloWorld,
  },
  mounted: function () {
    this.darkMode();
    // this.boxes();
  },
  methods: {
    darkMode: function () {
      new Darkmode().showWidget();
    },
    legoBox: function () {
      // const ctx = myCanvas.getContext("2d");
      // const legra = new Legra(ctx);
      // // console.log();
      // console.log(legra);
    },
    boxes: function () {},
  },
};
</script>
