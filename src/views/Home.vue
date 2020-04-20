<template>

  <div  class="home"> 
    

   
    

   <img src="https://i.imgur.com/LodfMQo.png" class="imgbtn" width=100%; draggable="false" alt="">
      <v-container  class="grey lighten-5 homealign ">
        
    <div>
    <div class="text-center mb-4">
      
    </div>
    <v-alert
      :value="alert"
      class="deep-purple accent-4"
      dark
      border="top"
     
      transition="scale-transition"
    >
    <h2>Frequently Asksed Questions</h2>
      Phasellus tempus. Fusce ac felis sit amet ligula pharetra condimentum. In dui magna, posuere eget, vestibulum et, tempor auctor, justo. Pellentesque posuere. Curabitur ligula sapien, tincidunt non, euismod vitae, posuere imperdiet, leo.

      Phasellus nec sem in justo pellentesque facilisis. Phasellus magna. Cras risus ipsum, faucibus ut, ullamcorper id, varius ac, leo. In hac habitasse platea dictumst. Praesent turpis.
    </v-alert>
  </div>z
      <v-btn  @click="alert = !alert" depressed class="deep-purple--text marginzed10" color="white">FAQ</v-btn>
      <v-btn to='/templates' depressed class="deep-purple--text marginzed11" color="white">Go to Templates</v-btn>
      <v-btn depressed class="deep-purple--text marginzed12" color="white">TOS</v-btn>
     
    
  </v-container>
    
  </div>
</template>

<script>



export default {
   data () {
      return {
        alert: false,
      }
    },
  
}
</script>

<style>

.home {
 
   

  text-align: center;

}
html .home {
  width: 100%;
height: 100%;
clip: auto;
position: absolute;
overflow: hidden;
}
html{
  overflow: hidden;
}
.marginzed10 {
  
  left: 60%;
}

.marginzed11 {
  left: 50%;
  
}



.marginzed12 {
 
  left: 40%;
  
}

.home .v-btn {
   position: absolute;
  top: 55%;
  
  transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  background-color: #555;
  color: white;
  font-size: 16px;
  
  padding: 12px 24px;
  border: none;
  cursor: pointer;
  border-radius: 5px;
  
}

.home .v-alert {
   position: absolute;
  top: 70%;
  left: 50%;
  transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  background-color: #555;
  color: white;
  font-size: 16px;
  
  padding: 12px 24px;
  border: none;
  cursor: pointer;
  border-radius: 5px;
  
}

h1 {
  font-family: Arial, Helvetica, sans-serif;
}




</style>



