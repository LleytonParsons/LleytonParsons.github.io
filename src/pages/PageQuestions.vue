<template>
    <div class="page-questions">
        <h1 class="header-text">Self-Diagnostic Questionnaire</h1>
        <div class="rectangle">
            <p class="question">1. Do your eyes hurt?</p>
            <!--{{ button-style }}-->
            <Button :style="{color: buttonColor}" class="button-style" @click="changeColor">Yes</Button>
            <Button :style="{color: buttonColor}" class="button-style" @click="changeColor">No</Button>
            <p class="question">2. Do you feel tired?</p>
            <p class="question">3. Have you been sitting down or standing up recently?</p>
            <p class="question">4. Have you walked away from this computer recently?</p>
            <p class="question">5. Focus your eyes on something far from this screen. Can you see it well?</p>
        </div>
    </div>
</template>

<script>
import Button from 'primevue/button'

export default{
    data() {
        return {
            buttonColor: 'black', selected:0
        }
    },
    methods: {
        changeColor() {
            this.buttonColor = this.buttonColor === 'black' ? 'blue' : 'black';
        }
    }
}
</script>

<style scoped>
.rectangle{
   width: center;
   height: 900px;
   background-color: rgb(227, 227, 227);
   display:grid;
   grid-template-columns: repeat(5);
   justify-content: center;
   align-items: center;
   border: 6px solid black;
}
.question{
    font-size: 32px;
    color: black;
    margin: 0;
    text-align: center;
    text-decoration: underline;
}

.button-style{
    border: 3px solid black;
    background: transparent;
    color: black;
    font-size: 24px;
}
.selected{
    color: rgb(0, 136, 255);
}
</style>