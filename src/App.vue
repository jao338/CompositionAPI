<template>

  <img alt="Vue logo" src="./assets/logo.png">

  <p>Alterando dados usando "reactive" - {{ user.first_name }} {{ user.last_name }}</p>
  <button @click="changeUser">Alterar</button>

  <br><br>

  <p>Alterando dados usando "ref" - {{ admin.first_name }} {{ admin.last_name }}</p>
  <button @click="changeAdmin">Alterar</button>
  
  <HelloWorld msg="Welcome to Your Vue.js App"/>

</template>

<script>
import { ref, reactive } from 'vue'
import HelloWorld from './components/HelloWorld.vue'

export default {

  name: 'App',
  
  components: {
    HelloWorld
  },

  mounted() {
    document.title = "Composition API"
  },

  setup(){

    const changeUser = () => {

      user.first_name = "Games";
      user.last_name = "Eduu";

    }

    const changeAdmin = () => {

      admin.value.first_name = "Blue";
      admin.value.last_name = "Pen";

    }

    const user = reactive({

      first_name: "Ednaldo",
      last_name: "Pereira",

    })

    const admin = ref({

      first_name: "Manoel",
      last_name: "Gomes",

    })

    return {
      user,
      admin,
      changeUser,
      changeAdmin,
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
