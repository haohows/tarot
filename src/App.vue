<template>
  <div id="app">
    <div class="imagesView">
      <div class="pic-box">
        <pic-zoom
          url="https://qqpublic.qpic.cn/qq_public/0/0-2249764024-3226A2D62B4A90C676066EE395342A43/0?fmt=jpg&size=23&h=889&w=500&ppv=1"
          :scale="3"
        ></pic-zoom>
      </div>
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
      url:
        "https://qqpublic.qpic.cn/qq_public/0/0-2249764024-3226A2D62B4A90C676066EE395342A43/0?fmt=jpg&size=23&h=889&w=500&ppv=1",
    };
  },
  methods: {},
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
.imagesView{
  /* border: 1px solid #eee; */
  width: 620px;
   margin: 0 auto;
}
</style>
