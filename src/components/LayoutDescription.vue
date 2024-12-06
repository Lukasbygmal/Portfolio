<template>
    <div class="layout-description-title">
      
      Student UU<br> Civilingenjör Informationsteknologi
    </div>
    <div class= "layout-description">
      Välkommen till min portfoliosida! Under utbildningen har jag både arbetat med många olika programmeringsspråk/teknologier som ni kan se nedan och lärt mig att kommunicera effektivt och samarbeta för att nå gemensamma mål från de projektarbeten jag haft.
      På min fritid spelar jag mycket brädspel, sitter med i KFUM Norrbyskärs styrelse och håller på med egna projekt, som ni kan se längre ner på sidan.
      Jag ser fram emot nya utmaningar där jag kan bidra med mina kunskaper och initativ för att utveckla lösningar som bidrar positivt till samhällsutvecklingen.
    </div>
  </template>
  
  <script>
  export default {
    name: 'LayoutDescription'
  }
  </script>
  
  <style scoped>
  .layout-description-title {
    font-size: 48px;
    font-weight: bold;
    color: black;
    margin: 22px;
    background-color: transparent;
  }
  .layout-description {
    font-size: 24px;
    color: black;
    margin: 5px 80px;
    background-color: transparent
  }
  
  @media (max-width: 768px) {
  .layout-description-title{
    font-size: 24px;
    margin: 4px;
  }
  .layout-description {
    font-size: 18px;
    color: black;
    margin: 15px;
  }
  .technologies {
    margin-top: auto;
    font-size: 0.9em;
    font-weight: bold;
    background-color: transparent;
    color: #BB4430;
  }
}
  </style>
  