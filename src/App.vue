<template>
  <div id="app">
    <div class="pic-box">
      <pic-zoom url="https://community.fansshare.com/pic15/w/sarmoung-brotherhood/1200/14145_rws_tarot_high_priestess.jpg" :scale="5"></pic-zoom>
    </div>
  </div>
</template>

<script>
import PicZoom from "./components/PicZoom";
export default {
  name: "App",
  components: {
    PicZoom,
  },
  data() {
    return {
      url: "https://community.fansshare.com/pic15/w/sarmoung-brotherhood/1200/14145_rws_tarot_high_priestess.jpg",
    };
  },
  methods: {

  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
  padding-bottom: 100px;
}
.pic-box {
  width: 300px;
  height: 500px;
  border: 1px solid #eee;
}
</style>
