<template>
  <div class="block" v-if="showBlock" @click="stopTimer">Click here {{delay}}</div>
</template>

<script>
export default {
    props:['delay'],
    data(){
        return{
            showBlock:false,
            score:0,
            timer:null,
        }
    },
    mounted(){
        setTimeout(() => {
            this.showBlock=true;//update
            this.startTimer()
        }, this.delay);
    },
    methods:{
        startTimer(){
            this.timer = setInterval(() => {
                this.score+=10;
            }, 10);
        },
        stopTimer(){
            clearInterval(this.timer);
            this.$emit("endGame",this.score)
        }
    }
    //updated work when something in data has changed
    // updated(){
    //     console.log('data updated')
    // },
    // unmounted(){
    //     console.log('unmounted')
    // }
}

</script>

<style>
    .block{
        background-color: #9c1de7;
        width: 200px;
        height: 200px;
        margin: 50px auto;
        padding: 50px;
        color: aliceblue;
        font-size: 20px;
        font-weight: bolder;
        cursor: pointer;
    }
</style>