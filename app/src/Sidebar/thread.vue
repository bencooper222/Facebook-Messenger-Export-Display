<template>
    <li id="thread">
    <div >
        <p id="name"> </p>
        <p id="id"> </p>    
    </div>
    </li>

</template>


<script>
    export default {
        name: 'Sidebar-Thread',
        data() {
            return {
                msg: 'Welcome to Your Vue.js App'
            }
        }
    }
</script>

<style lang="scss">
    #thread {
        width: 100%;
        background-color: white;
        border-bottom: 1px solid black;
        height: 15%;
        
    }
</style>