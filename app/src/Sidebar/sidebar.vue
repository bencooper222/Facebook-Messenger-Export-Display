<template>
   <div id="sidebar" onload="loadManifest">
      <div id="primaryUser">{{user}}</div>
      <ul id="threadList">
         <li v-for="thread in this.manifest" id="threadSidebar">
            <div>
                <p id="id">{{thread.UID}}</p>
               <ul id="paricipantList">
                    <li v-for="person in thread.Participants">
                      <div v-bind:title="person.Name"> {{getInitials(person.Name)}}</div>
                    </li>
                </ul>              
            </div>
         </li>
      </ul>
   </div>
</template>

<script>
    export default {
        name: 'Sidebar',

        data() {
            return {
                manifest: null,
                user: "Ben Cooper"
            }
        },
        mounted: function() {
            var _this = this; //this in not the this you were looking for
            this.loadManifest("jsons/manifest2.json", function(data) {

                _this.manifest = JSON.parse(data);

            });
        },

        methods: {
            loadManifest(location, callback) {

                var xobj = new XMLHttpRequest();
                xobj.overrideMimeType("application/json");
                xobj.open('GET', location, true); // Replace 'my_data' with the path to your file
                xobj.onreadystatechange = function() {
                    if (xobj.readyState == 4 && xobj.status == "200") {
                        // Required use of an anonymous callback as .open will NOT return a value but simply returns undefined in asynchronous mode
                        callback(xobj.responseText);
                    }
                };
                xobj.send(null);
            },
            getInitials(name) {
                var split = name.split(' ');
                var rtn = "";
                for(var i=0; i<split.length; i++){
                    rtn+= split[i][0];
                }
                return rtn;
            }

        }
    }
</script>

<style lang="scss">
    #sidebar {
        float: left;
        width: 20%;
        background-color: rebeccapurple;
        height: 100%;
        position: fixed;
    }
    
    #threadSidebar {
        width: calc(100% - 1px); 
        background-color: white;
        border-bottom: 1px solid black;
        border-right: 1px solid black;
        height: calc(15%-1px);
        margin: 0px;
    }

    #primaryUser{
        font-family: 'Khula', sans-serif;
        font-size: 35px;
    }

    #threadList{
        margin-top:10px;
    }
</style>