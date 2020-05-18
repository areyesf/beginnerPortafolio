<template>
  <div class="container">
    <div class="wrap">
      <div class="result">
        <div :class="[forma,color]"></div>
      </div>
      <!-- END-RESULT -->
      <div class="circles">
        <div class="circle red" v-on:click="changeColor('red')"></div>
        <div class="circle blue" v-on:click="changeColor('blue')"></div>
        <div class="circle green" v-on:click="changeColor('green')"></div>
      </div>
      <!-- END-CIRCLES -->
    </div>
  </div>
</template>
<script>
export default {
  name: "ColorSwap",
  data() {
    return {
      forma:'square',
      color:"red"
    };
  },
  methods: {
    changeColor(color) {
      this.color = color;
    },
  },
};
</script>

<style scoped lang="scss">
.container {
  width: 100%;
  height: 90vh;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  background-color: rgb(218, 238, 248);
  .wrap {
    width: 30%;
    .result {
      width: 100%;
      .square {
        width: 100%;
        height: 200px;
        border-radius: 10px;
        border: 10px solid white;
        box-shadow: 5px 5px 5px rgba(0, 0, 0, 0.4);
        transition: background ease-in-out 0.3s;
      }
    }
    .circles {
      display: flex;
      width: 100%;
      margin: 1rem 0;
      padding: 0.5rem;
      justify-content: space-around;
      .circle {
        width: 100px;
        height: 100px;
        border-radius: 50%;
        /* background-color: blue; */
        border: 10px solid white;
        cursor: pointer;
        box-shadow: 5px 5px 5px rgba(0, 0, 0, 0.4);
        transition: box-shadow ease-in-out 0.2s;
        &:hover {
          box-shadow: none;
        }
      }
    }
    .red {
      background: rgb(175, 36, 36);
    }
    .blue {
      background: rgb(19, 19, 80);
    }
    .green {
      background: rgb(21, 138, 74);
    }
  }
}
@media (max-width: 1300px) {
  .container {
    .wrap {
      padding: 0 1rem;
      width: 50%;
    }
  }
}
// TABLET
@media (max-width: 850px) {
  .container {
    .wrap {
      padding: 0 1rem;
      width: 50%;
    }
  }
}
@media (max-width: 550px) {
  .container {
    .wrap {
      // padding: 0 1rem;
      width: 100%;
    }
  }
}
</style>
