<template>

  <img alt="Vue logo" src="./assets/logo.png">

  <exampleComponent data-vue="BluePen" @update="getUpdate">
    
    <span>Save</span>

    <template #icon> Icon</template>

  </exampleComponent>


</template>

<script>
import exampleComponent from './components/exampleComponent.vue'

export default {

  name: 'App',
  
  components: {
    exampleComponent,
  },

  setup(){

    const getUpdate = (data) => {
      console.log('getUpdate', data);
    }

    return{
      getUpdate,
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
