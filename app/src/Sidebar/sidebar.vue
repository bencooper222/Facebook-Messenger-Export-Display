<template>
    <div id="sidebar">
        <div id="primaryUser"></div>
        <ul id="threadList"> </ul>
    </div>
</template>


<script>
    export default {
        name: 'Sidebar',
        data() {
            return {
                msg: 'Welcome to Your Vue.js App'
            }
        }
    }
</script>

<style lang="scss">
    #sidebar{
        float: left;
        width: 20%;
        background-color: rebeccapurple;
        height: 100%;
        position: absolute;
    }
</style>