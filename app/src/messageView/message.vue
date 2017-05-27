<template>
  
<div id="messageLine" >
    <div id="messageBubble" :title="createHoverText()"> {{Text}} </div>
    </div>
</template>


<script>
    export default {
        props: ['msg','isPrimary'],
        name: 'message',
        data() {
            return {
                Text: this.msg.Text,
                SentTime: this.msg.SentTime,
                SenderID: this.msg.SenderID,
                SenderName: this.msg.SenderName
            }
        },
        methods: {
            createHoverText() {
                return "Sent by " + this.SenderName + " at " + this.SentTime.Time;
            }
        }
    }
</script>

<style lang="scss">

</style>