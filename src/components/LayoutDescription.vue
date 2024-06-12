<template>
    <div class="layout-description-title">
      Civilingenjör IT Uppsala Universitet
    </div>
    <div class= "layout-description">
      Jag är en engagerad systemutvecklare med en civilingenjörsexamen i informationsteknik från Uppsala universitet. Med flera års erfarenhet inom mjukvaruutveckling har jag utvecklat en stark kompetens inom hela utvecklingscykeln, från kravinsamling till implementation och testning.
      Jag har arbetat med olika programmeringsspråk, inklusive Java, Python, och JavaScript, samt moderna ramverk som React och Angular. Genom mitt arbete i agila team har jag lärt mig att kommunicera effektivt och samarbeta för att nå gemensamma mål.
      Min passion för teknologi driver mig att ständigt uppdatera mina kunskaper och jag är särskilt intresserad av att skapa robusta och skalbara system som verkligen gör skillnad. På min fritid bidrar jag till open source-projekt och utforskar nya teknologier för att bredda min kompetens.
      Jag ser fram emot nya utmaningar där jag kan bidra med mina kunskaper och erfarenheter för att utveckla innovativa lösningar.
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
  