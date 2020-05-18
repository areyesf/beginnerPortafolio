<template>
  <div class="nav">
    <router-link to="/">Inicio</router-link> |
    <router-link to="/colorswap">ColorSwap</router-link> |
    <router-link to="/counter">Counter</router-link> |
    <router-link to="/countdown">CountDown</router-link> |

  </div>
</template>

<style scope lang="scss">
.nav {
  height: 10vh;
  padding: 30px;
  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
