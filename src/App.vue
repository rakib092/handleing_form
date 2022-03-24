<template>
   <div class="container my-3">
       <button @click="componentToRender='CompHome'">Home</button>
       <button @click="componentToRender='CompAbout'">About</button>
       <button @click="componentToRender='CompContact'">Contact</button>
      
       <keep-alive>
        <component :is="componentToRender"></component>
       </keep-alive>
   </div>
</template>

<script>
import CompHome from './components/Home_page';
import CompAbout from './components/About_us';
import CompContact from './components/Contact_us';
export default {
   data() {
     return {
        componentToRender:'CompContact',
     }
   },
   components:{
      CompHome,
      CompAbout,
      CompContact,
   },
  
  
}
</script>