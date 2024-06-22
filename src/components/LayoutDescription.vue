<template>
    <div class="layout-description-title">
      IT Student Uppsala Universitet
    </div>
    <div class= "layout-description">
      Välkommen till min portfoliosida! Jag är student på civilingenjörsprogrammet i informationsteknik på Uppsala Universitet.
      Jag har arbetat med olika programmeringsspråk, som C, Java, Python, SQL, och JavaScript, samt moderna ramverk som React och Flutter. I de projektarbeten jag haft under utbildningen har jag lärt mig att kommunicera effektivt och samarbeta för att nå gemensamma mål.
      Att få lära sig ny saker är bland det bästa jag vet och försöker alltid lära mig nya saker. På min fritid håller jag på med egna projekt, som ni kan se längre ner på sidan, och utforskar nya teknologier för att bredda min kompetens.
      Jag ser fram emot nya utmaningar där jag kan bidra med mina kunskaper och erfarenheter för att utveckla lösningar som bidrar positivt till samhällsutvecklingen.
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
}
  </style>
  