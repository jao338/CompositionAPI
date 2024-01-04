<template>

  <img alt="Vue logo" src="./assets/logo.png">

  <br><br>

  <p>Alterando dados usando "ref" - {{ adminFullName }}</p>
  <button @click="changeAdmin">Alterar</button>
  
  <HelloWorld msg="Welcome to Your Vue.js App"/>

</template>

<script>
import { ref, computed, watch } from 'vue'
import HelloWorld from './components/HelloWorld.vue'

export default {

  name: 'App',
  
  components: {
    HelloWorld
  },

  setup(){

    const adminFullName = computed(() => {
      return `${admin.value.first_name} ${admin.value.last_name}`
    })

    const changeAdmin = () => {

      admin.value.first_name = "Blue";
      admin.value.last_name = "Pen";

    }

    const admin = ref({

      first_name: "Manoel",
      last_name: "Gomes",

    })

    watch(admin, () => {
      console.log("Usuário alterado")
    },{
      deep: true
    })

    return {
      admin,
      changeAdmin,
      adminFullName,
    }

  }

}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
