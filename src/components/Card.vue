<template>
  <div class="card">
    <ul v-for="card in arrayCard" :key="card.name">
      <li>
        <img :src="card.src" alt="card.alt" style="width: 100px;">
        {{ card.name }}  - {{ card.age }}
      </li>
    </ul>
  </div>
</template>

<script>
import { defineComponent } from 'vue';
export default defineComponent( {
  name: 'CardQ',
  props:{
    arrayCard: Array
  },
  setup(){
    
return {
  
}
  }
})
</script>

<style >
ul{list-style: none;}
</style>
