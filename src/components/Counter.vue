<template>
  <div>
    <div class="container">
      <div class="wrap">
        <div class="counter" >
          <button class="btn" v-on:click="disminuir">-</button>
          <p>{{contador}}</p>
          <button class="btn" v-on:click="aumentar">+</button>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Counter",
  data() {
    return {
      contador: 0,
    };
  },
  methods: {
      aumentar(){
          this.contador++
      },
      disminuir(){
          this.contador--
      }
  },
};
</script>
<style scoped lang="scss">
.container {
  width: 100%;
  height: 90vh;
  background-color: rgb(120, 199, 179);
  display: flex;
  align-items: center;
  justify-content: center;
  .wrap {
    widows: 50%;
    .counter {
      display: flex;
      align-items: center;
      justify-content: center;
      p {
        font-size: 4rem;
        font-weight: bold;
        color: white;
      }
      .btn {
        border: none;
        margin: 0 3rem;
        color: rgb(56, 56, 110);
        font-size: 3rem;
        font-weight: bold;
        border-radius: 50%;
        width: 100px;
        height: 100px;
        background-color: white;
        cursor: pointer;
        transition: font-size ease 0.1s;
        @media (max-width: 550px) {
          margin: 0 1rem;
        }
        &:hover {
          font-size: 4rem;
        }
      }
    }
  }
}
@media (max-width: 550px) {
  .wrap {
    width: 100%;
  }
}
</style>
