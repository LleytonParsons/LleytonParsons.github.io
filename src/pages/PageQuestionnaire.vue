<template>
    <div class="page-questionnaire">
        <h1 class="header-text">Take a Questionnaire</h1>
    </div>
    <div id="quest-menu">
        <div class="regular-text">Aren't sure if you need a break?</div>
    </div>
    <div class="warning-text">DISCLAIMER: This questionnaire is NOT professional.
        Please seek professional help for more serious issues.
    </div>
</template>

<style scoped>
#quest-menu {
  max-width: 1280px;
  margin: 0 auto;
  font-weight: normal;
  display: grid;
  grid-template-rows: repeat(2, auto);
  gap: 0px;
}

.regular-text{
    font-family: serif;
    font-size: 48px;
    color: black;
}
.warning-text{
    text-decoration: underline;
    font-size: 24px;
    color: red;
    padding-left: 80px;
}
</style>