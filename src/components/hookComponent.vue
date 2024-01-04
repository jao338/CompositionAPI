<template>
  <div>
    Hook
  </div>
</template>

<script>
import { 
    
    onBeforeMount,
    onMounted,
    onBeforeUnmount,
    onUnmounted,

} from "vue"

export default {

    setup(){

        onBeforeMount(() => {
            console.log("onBeforeMount - Antes de montar")
        })

        onMounted(() => {
            console.log("onMounted - Após montar")
        })

        onBeforeUnmount(() => {
            console.log("onBeforeUnmount - Antes de desmontar")
        })

        onUnmounted(() => {
            console.log("onUnmounted - Após desmontar")
        })

    }

}
</script>

<style>

</style>