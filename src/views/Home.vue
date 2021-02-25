import { mapState } from 'vuex';
<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <!-- <h1>Contador: {{ $store.state.contador }}</h1> -->
    <h1 :style="colorContador">Mi contador: {{ contador }}</h1>

    <!-- <button @click="incrementar">AUMENTAR</button> -->
    <button @click="accionIncrementar">AUMENTAR</button>

    <BtnDisminuir />

  </div>
</template>

<script>
import BtnDisminuir from '../components/BtnDisminuir'

import { mapActions } from 'vuex'

export default {
  name: 'Home',
  components: {
    BtnDisminuir
  },

  computed: {
    ...mapState(['contador']),
    colorContador() {
      return [this.contador > 100 ? {'color': 'green'} : {'color': 'red'}]
    }
  },

  methods: {
    ...mapMutations(['incrementar']),
    ...mapActions(['accionIncrementar'])
  }
}
</script>
