<template>
  <div id="app">
    <div class="wrap">
      <div class="imagesView">
        <div class="pic-box">
          <pic-zoom
            :url="cardData.url"
            :scale="scale"
            ref="reverseApp"
          ></pic-zoom>
        </div>
      </div>
      <div class="controArea">
        <div class="icon-search">
          <i class="fas fa-search-plus"></i>
        </div>

        <div class="card mb-5 shadow card-description">
          <h5 class="card-header">牌面描述</h5>
          <div class="card-body">
            <h5 class="card-title">{{ cardData.name }}</h5>
            <div class="cardTextArea">
              <p class="card-text">
                {{ cardData.text }}
              </p>
            </div>
          </div>
        </div>

        <div class="input-group mb-3 shadow">
          <div class="input-group-prepend">
            <label class="input-group-text">卡片名稱</label>
          </div>
          <select class="custom-select" v-model="cardData">
            <!-- <option selected disabled>
              -- 請選擇卡片 --
            </option> -->
            <option v-for="item in card" :key="item.id" :value="item">
              {{ item.name }}
            </option>
          </select>
        </div>

        <div class="btn-group hadow" role="group">
          <button class="btn btn-dark" disabled>放大倍率</button>
          <button
            class="btn btn-outline-dark"
            @click="changeScale(2)"
            :class="{ active: scale == 2 }"
          >
            2x
          </button>
          <button
            class="btn btn-outline-dark"
            @click="changeScale(3)"
            :class="{ active: scale == 3 }"
          >
            3x
          </button>
          <button
            class="btn btn-outline-dark"
            @click="changeScale(4)"
            :class="{ active: scale == 4 }"
          >
            4x
          </button>
          <button
            class="btn btn-outline-dark"
            @click="changeScale(5)"
            :class="{ active: scale == 5 }"
          >
            5x
          </button>
        </div>
        <button
          class="btn btn-dark shadow"
          style="margin-left: 79px"
          @click="activeReverse"
        >
          <span v-if="isReverse">正位</span>
          <span v-else>逆位</span>
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import PicZoom from "./components/PicZoom";
import data from "./assets/cardData";
export default {
  name: "App",
  components: {
    PicZoom,
  },
  data() {
    return {
      cardData: {
        url: "./static/init.jpg",
        name: "咬咬咬",
        text: "這是隻正在咬網路線的電氣鼠。",
      },
      scale: 2,
      isReverse: false,
    };
  },
  computed: {
    card() {
      return data;
    },
  },
  methods: {
    changeScale(val) {
      this.scale = val;
    },
    activeReverse() {
      this.isReverse = !this.isReverse;
      this.$refs.reverseApp.$emit("rotateX2");
    },
  },
};
</script>

<style >
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  user-select: none;
}
.wrap {
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
.pic-box {
  width: 300px;
  height: 500px;
  border: 1px solid #eee;
}
.imagesView {
  /* border: 1px solid #eee; */
  width: 620px;
}

.card-description {
  height: 360px;
}
</style>


<style lang="scss" scoped>
.cardTextArea {
  height: 240px;
  overflow: auto;
  &::-webkit-scrollbar {
    width: 10px;
    height: 3px;
    background-color: transparent;
  }

  &::-webkit-scrollbar-thumb {
    border-radius: 10px;
    background-color: rgba(179, 179, 179, 0.3);
    &:hover {
      background-color: rgba(58, 58, 58, 0.3);
    }
  }
  &::-webkit-scrollbar-track {
    background-color: transparent;
  }
}

.controArea {
  position: relative;
  width: 400px;
  height: 500px;
  .icon-search {
    position: absolute;
    top: 0;
    left: -314px;
    font-size: 50px;
    color: rgb(221, 221, 221);
    width: 300px;
    height: 500px;
    background-color: rgba(233, 233, 233, 0.466);
    display: flex;
    justify-content: center;
    align-items: center;
  }
}
</style>