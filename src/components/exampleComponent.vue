<template>
  
    <button @click="sendData">
        <slot></slot>
        <slot name="icon"></slot>
    </button>

</template>

<script>
export default {

    props: {
        variant: {
            type: String,
            default: "success",
        },
    },

    setup (props, { emit }){
        const sendData = () => {
            emit('update', true)
        }

        return {
            sendData
        }
    }

}
</script>

<style>

    button{
        padding-left: 8px;
        padding-right: 8px;
        padding-top: 4px;
        padding-bottom: 4px;
    }

</style>