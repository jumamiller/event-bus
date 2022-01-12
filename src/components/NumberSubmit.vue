<template>
  <div class="container">
    <input type="text" v-model="number" />
    <button @click="addNumber">Add New Number</button>
  </div>
  <NumberDisplay/>
</template>

<script>
import {eventBus} from "@/assets/js/event-bus";
import NumberDisplay from "@/components/NumberDisplay.vue";
export default {
  name: "NumberComponent",
  data(){
    return{
      number: 0
    }
  },
  methods: {
    addNumber(){
      eventBus.emit('number-added', Number(this.number));
    }
  },
  components:{
    NumberDisplay
  }
}
</script>

<style scoped>

</style>
