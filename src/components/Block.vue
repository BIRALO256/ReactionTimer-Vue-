<template>
    <div class="block"  v-if="showBlock">
        {{ delay }}
    </div>
</template>

<script>


export default ({
    props:[
        'delay'
    ],

    data(){
        return{
        showBlock:false
        }
    },

    mounted(){
        // you do some stuff here when the componet in mounted on the DOM
        setTimeout(()=>{}, this.delay) // when his component is being mounted we set some time which we passed a prop
    },

    updated(){


    }

})
</script>

<style scoped>
  
  .block{
    width: 400px;
    border-radius: 20px;
    background: rgb(65, 122, 65);
    color: white;
    text-align: center;
    padding:100px;
    margin:40px auto;
  }

</style>