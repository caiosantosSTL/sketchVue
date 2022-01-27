<template>
  <div class="container">
    <p>{{ ax }}</p>
    <botao-emit @mudandoGo="mudou()" />
    <h1 :v-model="textodata">{{ textodata }}</h1>
    <div>
      <ul>
        <li :key="index" v-for="(arraydata, index) in arraydatas">
          {{ arraydata.nome }}
        </li>
      </ul>
    </div>

    <div>
      <p :key="index" v-for="(arraydataB, index) in arraydatasB">
        {{ arraydataB }}
      </p>
    </div>

    <div>
      <p v-if="booldata">Aparece se verdadeiro</p>
      <p v-else>Aparece se falso</p>
      <button class="btn bg-success" @click="boolFunc">mudar bool</button>
    </div>

    <div class="mt-5 d-flex flex-row flex-wrap">
      <input class="me-4" type="text" placeholder="Algum texto aqui" ref="inputid">
      <button class="btn bg-primary me-4" @click="getElement">Mudar aqui</button>
      <p class="me-4" ref="thisid">Texto que será mudadado</p>
    </div>
    
  </div>
</template>

<script>
import BotaoEmit from "./BotaoEmit.vue";
export default {
  components: { BotaoEmit },
  name: "TestBootstrap",
  props: {
    ax: String,
  },
  data() {
    return {
      textodata: "Olha o textodata",
      arraydatas: [
        { nome: "Jonas" },
        { nome: "Lira" },
        { nome: "Tina" },
        { nome: "Timop" },
        { nome: "Nikol" },
      ],
      arraydatasB: ["oi", "meu", "amigo", "como", "vai"],
      booldata: true,
    };
  },
  methods: {
    mudou() {
      this.textodata = "Mudou galera";
    },

    boolFunc() {
      this.booldata = !this.booldata;
    },

    getElement(){
      var inputx = this.$refs.inputid.value
      var dd = this.$refs.thisid.textContent
      this.$refs.thisid.innerText = inputx
      console.log(inputx);
    },
  },
};
</script>

<style scoped>
</style>