<template>
  <component v-bind:is="currentComponent" :parameter="parameter" />
</template>

<script>
  import ShowAll from './ShowAll'
  import Add from './Add'
  import Modify from './Modify'
  export default {
    name: "Studio",
    data(){
      return{
        components : {
          ShowAll : ShowAll,
          Add : Add,
          Modify : Modify
        },
        currentComponent : ShowAll,
        parameter : null
      }
    },
    methods : {
      showComponent(component) {
        this.currentComponent = component;
      }
    },
    mounted(){

      //在组件挂载完成后向父组件发送title事件,使得父组件修改标题
      this.$emit('title','演出厅管理');
    }
  }
</script>

<style scoped>

</style>
