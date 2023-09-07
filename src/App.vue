<template>
<Cards/>
<h2 class="hello"> hello, {{ name }}</h2>

 <div class="container">
  <button @click="flag=!flag">click</button>
  <h2 v-if="flag">Hello</h2>
  <h2 v-else>Bye bye</h2>
 </div>

 <div class="contaoner-2">
  <button @click="count++">Click+1</button>
  <H2>{{ count }}</H2>
 </div>

 <div class="container-3">
  <input type="text" v-model="text">
  <p> {{ text }}</p>
 </div>
</template>

<script>
import Cards from "@/components/Cards"
import{defineComponent, ref} from "vue";

export default defineComponent( {
  name: 'App',
  components: {
    Cards
  },
  setup(){
    const name = "Yuriy"
    const flag = ref(true)
    const count = ref(0)
    const text = ref("")
    return { name,
             flag,
             count,
             text
    }
  }
})
</script>

<style>
.hello{
  text-align: center;
}
</style>
