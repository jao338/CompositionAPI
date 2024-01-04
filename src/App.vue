<template>

  <img alt="Vue logo" src="./assets/logo.png">

  <br><br>

  <p>Alterando dados usando "ref" - {{ adminFullName }}</p>
  <button @click="changeAdmin">Alterar</button>

  <br><br>

  <hookComponent v-if="showHook"/><br>
  <button @click="showHook = !showHook">Mostrar/Ocultar</button>


</template>

<script>
import { ref, computed, watch } from 'vue'
import hookComponent from './components/hookComponent.vue'

export default {

  name: 'App',
  
  components: {
    hookComponent,
  },

  setup(){

    const showHook = ref(true)

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
      showHook
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
