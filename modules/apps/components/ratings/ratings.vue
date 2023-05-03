
 
    
<template>
  <a-progress :percent="30" />
  <a-progress
    :percent="50"
    status="active"
  />
  <a-progress
    :percent="70"
    status="exception"
  />
  <a-progress :percent="100" />
  <a-progress
    :percent="50"
    :show-info="false"
  />
</template>


    <script lang="ts">
      export default {
      name: 'Ratings',
      
      props: {
      component: {
      type: Object,
      required: true
      }
      },
    
      }
    </script>
    <style
      lang="scss"
      scoped
    >
      .sectionTitle {
      padding-left: 23px;
      font-size: 1.5vw;
      font-weight: bold;
      margin-bottom:0.7vw ;
      margin-left:9Vw ;
      }
      .card {
      width:19.5vw;
      height: 24.5vw;
      max-width: 50%;
      margin: auto;
      border: 1px solid lightgray;
      border-radius: 3%;
       
      .container {
          
        
  
          
      .cover {
      position: absolute; /* Pour que l'image de couverture se positionne par-dessus les autres éléments */
      top: 0;
      left: 0;
      width: 100%; /* Pour que l'image de couverture prenne toute la largeur du conteneur */
      height: 100%; /* Modifier la hauteur à 50% pour que l'image de couverture prenne la moitié de la hauteur de la carte */
   
      }
      .headings{
      margin-top: 17vw;
    
      position: absolute; /* Pour que l'image de couverture se positionne par-dessus les autres éléments */
      left: 0%;
      right: 0%;
      bottom:0%;
      top: 13%;
      background-color: rgb(49, 45, 45);
      opacity: 0.75;
           
      .title {
      font-weight: bold;
      font-size: 0.7vw;
      color: hsl(96, 12%, 92%) ;     
      position: absolute; /* Pour que l'image de couverture se positionne par-dessus les autres éléments */
      left: 20%;
      right: 0%;
      bottom:0%;
      top: 19%;
      }
      .sub-title{
      position: absolute; /* Pour que l'image de couverture se positionne par-dessus les autres éléments */
      left: 9.9%;
      right: 0%;
      bottom:0%;
      top: 19%;
            
      font-size: 0.6vw;
      margin:0.3VW;
      color: hsl(96, 12%, 92%)  
      }
      .thumbnail{
      width:2.5vw;
      height: 2.5vw;
      border-radius: 10%;
      margin:0.7VW;
      }
           
         
      }
          
      }
      }
    </style>
 