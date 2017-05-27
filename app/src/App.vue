<template>
  
  <div id="app">
    <sidebar> </sidebar>
    <thread> </thread>
  </div>
</template>


<script>
  import Sidebar from './Sidebar/sidebar.vue';
  import Thread from './messageView/thread.vue'

    export default {
      components: {'sidebar': Sidebar,'thread':Thread},
        name: 'app',
        data() {
            return {
                msg: 'Welcome to Your Vue.js App'
            } 
        }
    }
</script>

<style lang="scss">
    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        height: 100%;
    }
     
 
    body, html{ // needed to make the main view full height
        height: 100%;
    }
       
    
    
    h1,
    h2 {
        font-weight: normal;
    }
    
    ul {  
        list-style-type: none;
        padding: 0;
    }
    
    li {
        display: inline-block;
        margin: 0 10px;
    }
    
    a {
        color: #42b983;
    }
  
</style>