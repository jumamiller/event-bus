<template>
  <div class="container">
    {{ number }}
  </div>
</template>

<script>
import {eventBus} from "@/assets/js/event-bus";

export default {
  name: "NumberDisplay",
  data(){
    return {
      number: [1,2,3,4,5,6,7,8,9,10]
    }
  },
  created() {
    eventBus.on('number-added', (number) => {
      this.number.push(number)
    })
  }
}
</script>

<style scoped>

</style>
