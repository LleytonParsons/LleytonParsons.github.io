<template>
    <div class="page-questions">
        <h1 class="header-text">Self-Diagnostic Questionnaire</h1>
        <div class="rectangle">
            <p class="question">1. Do your eyes hurt?</p>
            <Button :style="{color: yesButtonColor}" class="button-style" @click="changeColor('yes')">Yes</Button>
            <Button :style="{color: noButtonColor}" class="button-style" @click="changeColor('no')">No</Button>
            <p class="question">2. Do you feel tired?</p>
            <Button :style="{color: yesButtonColor}" class="button-style" @click="changeColor('yes')">Yes</Button>
            <Button :style="{color: noButtonColor}" class="button-style" @click="changeColor('no')">No</Button>
            <p class="question">3. Have you been sitting down or standing up recently?</p>
            <Button :style="{color: yesButtonColor}" class="button-style" @click="changeColor('yes')">Sitting</Button>
            <Button :style="{color: noButtonColor}" class="button-style" @click="changeColor('no')">Standing</Button>
            <p class="question">4. Have you walked away from this computer recently?</p>
            <Button :style="{color: yesButtonColor}" class="button-style" @click="changeColor('yes')">Yes</Button>
            <Button :style="{color: noButtonColor}" class="button-style" @click="changeColor('no')">No</Button>
            <p class="question">5. Focus your eyes on something far from this screen. Can you see it well?</p>
            <Button :style="{color: yesButtonColor}" class="button-style" @click="changeColor('yes')">Yes</Button>
            <Button :style="{color: noButtonColor}" class="button-style" @click="changeColor('no')">No</Button>
        </div>
    </div>
</template>

<script>
import Button from 'primevue/button'

export default{
    data() {
        return {
            yesButtonColor: 'black',
            noButtonColor: 'black'
        }
    },
    methods: {
        changeColor(button) {
            if(button === 'yes'){
                this.yesButtonColor = this.yesButtonColor === 'black' ? 'blue' : 'black';
            } else if (button === 'no'){
                this.noButtonColor = this.noButtonColor === 'black' ? 'blue' : 'black';
            }
        }
    }
}
</script>

<style scoped>
.rectangle{
   width: center;
   height: 1500px;
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