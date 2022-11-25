
<script>
export default {
    name: "CityComponent",
    
    props: {
      name: String,
      country_name: String,
      country_code: String,
      state_name: String,
      state_code: String,
      latitude: String,
      longitude: String
    }
};

</script>
  
<style scoped>
.city { 
    padding: 2px; 
    white-space: nowrap; 
    width: 350px; 
    height: 350px; 
    border-style: solid; 
    border-radius: 5px; 
    border-color: grey; 
  } 
   
  h1 { 
    overflow: hidden; 
    text-overflow: ellipsis; 
  } 

</style>

<template>

    <div class="city">
    <!-- Comment --><h1> Pais {{ country_name  || 'No props passed yet' }}</h1>
    <!-- Comment --><p> Estado{{ state_name  || 'No props passed yet' }}</p>
    <!-- Comment --><p> Latitud {{ latitude || 'No props passed yet' }}</p>
   <!-- Comment --> <p> Longitud {{ longitude  || 'No props passed yet' }}</p>
   <img src="@/assets/city.jpg" alt="ciudad pe" style="width:290px;height:210px;">
    </div>
    
</template>


