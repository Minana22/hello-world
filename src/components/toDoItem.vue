<template>
    <div>
        <input type="checkbox" :id="id" v-bind:checked="isDone"/>
        <label :for="id">{{label}}</label>

    </div>

</template>

<script>
 


    export default{
        props:{
            label: {required:true, type: String},
            done:{default:false, type: Boolean}
            
        },
        data(){
            return{
                isDone: this.done,
               id: id

            };
        }
        
    };

</script>