<template>
  <main :class="{'clicked':isOpen}" @click="defaultMode">
    <the-button
            v-for="index in (0, 4)"
            :key="index"
            :id="index"
            :is-clicked="isOpen === index"
            @clicked="clickManager"
    />
  </main>
</template>

<script>
  import theButton from './components/the-button'
  export default {
    name: 'App',
    components: {
      theButton
    },
    data(){
      return{
        isOpen: null,
        wasOpen: null
      }
    },
    methods:{
      clickManager(id){
        this.wasOpen = this.isOpen;
        this.isOpen = id;
        if (this.wasOpen === this.isOpen) this.isOpen = null;
      },
      defaultMode(){
        if (this.isOpen !== null)this.isOpen = null;
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
  }
  .clicked{
    cursor: pointer;
  }
  main{
    background-color: #F8F8F8;
    display: flex;
    justify-content: space-evenly;
    flex-wrap: wrap;
    padding-top: 120px;
    box-sizing: border-box;
    min-height: 100vh;
  }

  body{
    margin: 0;
  }
</style>
