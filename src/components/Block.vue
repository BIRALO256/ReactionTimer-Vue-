<template>
    <div class="block"  v-if="showBlock" @click="stopTimer">
        {{ delay }}
        {{ reactionTime }}
    </div>
</template>

<script>


export default ({
    props:[
        'delay'
    ],

    data(){
        return{
        showBlock:false,
        timer: null,
        reactionTime:0,
        }
    },

    mounted(){
        // you do some stuff here when the componet in mounted on the DOM
        setTimeout(()=>{
            this.showBlock =true
            this.startTimer()
        }, this.delay) // when his component is being mounted we set some time which we passed a prop
    },

    updated(){


    },

    methods:{
        startTimer(){
            this.timer =setInterval(() => {
                this.reactionTime +=10
            }, 10);
        },
        stopTimer(){
            clearInterval(this.timer)
            this.$emit('end',this.reactionTime)
        }
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