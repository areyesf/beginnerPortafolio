<template>
  <div>
    <div class="container">
      <div class="wrap">
        <form action="">
          <input type="date" v-model="limiteFecha" />
          <button v-on:click="calcularTiempo">Calcular</button>
        </form>
        <div class="result">
          <p>
            Falta
            <span>{{ dias }}</span>
            dias,
            <span>{{ horas }}</span>
            horas,
            <span>{{ minutos }}</span>
            minutos y
            <span>{{ segundos }}</span>
            segundos
          </p>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      limiteFecha: "",
      annos: 0,
      meses: 0,
      dias: 0,
      horas: 0,
      minutos: 0,
      segundos: 0,
    };
  },
  methods: {
    calcularTiempo(e) {
      e.preventDefault();
      const strFechaLimite = `${this.limiteFecha} 00:00:00`
      const fechaLimite = new Date(strFechaLimite).getTime();
      
      setInterval(() => {
        const ahora = new Date().getTime();
        const diferencia = fechaLimite - ahora;

        this.dias = Math.floor(diferencia / 86400000);
        this.horas = Math.floor((diferencia % 86400000) / 3600000);
        this.minutos = Math.floor((diferencia % (3600000)) / (60000));
        this.segundos = Math.floor((diferencia % (60000)) / (1000));
      }, 1000);
    },
  },
};
</script>
<style scoped lang="scss">
.container {
  width: 100%;
  min-height: 90vh;
  background-color: rgb(128, 0, 38);
  display: flex;
  align-items: center;
  justify-content: center;
  .wrap {
    width: 50%;
    @media (max-width: 750px) {
      width: 100%;
      padding: 0 1rem;
    }
    form {
      display: flex;
      flex-direction: column;
      margin: 1rem 0;
      input {
        border: none;
        padding: 1rem;
        width: 100%;
        font-size: 1.5rem;
        text-align: center;
        color: gray;
        margin: .5rem 0;
      }
      button {
        padding: 0.5rem;
        border: none;
        background: teal;
        color: white;
        font-size: 1rem;
        cursor: pointer;
        transition: all ease 0.2s;
        &:hover {
          background: tomato;
        }
      }
    }
    .result {
      color: white;
      font-size: 2rem;
      span {
        color: yellowgreen;
        font-weight: bold;
      }
    }
  }
}
</style>
