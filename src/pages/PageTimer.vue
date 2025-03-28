<template>
    <div class="page-timer">
        <h1 class="header-text">Set a Timer</h1>
        <h1 class="timer">Timer:{{ seconds }} second(s)...</h1>
        <button @click="startTimer">Start</button>
        <button @click="stopTimer">Stop</button>
        <button @click="resetTimer">Reset</button>
    </div>
</template>

<script>
export default{
    data(){
        return {
            seconds: 180,
            timer: null
        }
    },
methods: {
    startTimer(){
        if(!this.timer){
            this.timer = setInterval(() => {
                this.seconds--;
                if(this.seconds === 0){
                    this.stopTimer()
                }
            }, 1000);
        }
    },
    stopTimer(){
        clearInterval(this.timer);
        this.timer = null;
    },
    resetTimer(){
        this.seconds = 180;
        this.stopTimer();
    }
},
    beforeDestroy(){
        this.stopTimer()
    }
}
</script>

<style scoped>
.timer{
    font-family:serif;
    font-size: 32px;
    color:black;
}
</style>