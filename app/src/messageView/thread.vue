<template>
  
  <div id="thread">
      <input v-model="uid" value=1>
      <ul id="messageView">
          <li v-for="message in messageText">
              <message :msg="message"> </message> 
            </li>
          </ul>    
     
  </div>    
</template>


<script>
    import Message from './message.vue'
    export default {
          components: {'message': Message},
        name: 'thread',
        data() {
            return {
                uid: 1, // default to 1
                messageText: null
            }
        },
        watch: {
            uid: function() {
                this.triggerMessageGet();
            }
        },
        mounted: function(){
            this.triggerMessageGet();
            console.log("hi");
        },
        methods: {
            getMessageText(callback) {
                var xobj = new XMLHttpRequest();
                xobj.overrideMimeType("application/json");
                xobj.open('GET', "jsons/" + this.uid + ".json", true); // Replace 'my_data' with the path to your file
                xobj.onreadystatechange = function() {
                    if (xobj.readyState == 4 && xobj.status == "200") {
                        // Required use of an anonymous callback as .open will NOT return a value but simply returns undefined in asynchronous mode
                        callback(xobj.responseText);
                    }
                };
                xobj.send(null);
            },
            triggerMessageGet() {
                var _this = this; //this in not the this you were looking for
                this.getMessageText(function(data) {

                    _this.messageText = JSON.parse(data);

                });
            }

            
        }
    }
</script>

<style lang="scss">
    #thread {
        width: 80%;
        background-color: rgba(211, 211, 211, .4);
        height: 100%;
        float: right;
        margin-left: 20%;
        position: relative;
        overflow: auto;
        z-index: 1;
    }
 
</style>