<template>
  <h1 @click="increase">
    {{ count }} / {{ doubleCount }}
  </h1>
  <h1 @click="changeMessage">
    {{ message }} / {{ reversedMessage }}
  </h1>
</template>

<script>
import {ref, computed, watch, onMounted} from "vue"
export default {
  setup() {
    // increase count 
    let count = ref(0)
    const doubleCount = computed(() => {
      return count.value * 2
    })
    function increase() {
      count.value += 1
    }
    console.log(count.value)
    

    let message = "Hello World!"
    const reversedMessage = computed(() => {
      return reversedMessage.value.split("").reverse().join("")
    })
    watch(message, (value) => {
       console.log(value)
    })
    function changeMessage() {
      message.value = "Good!"
    }
    onMounted(()=> {
      console.log(message.value)
    })

    return {
      count, doubleCount, increase, message, reversedMessage, changeMessage, 
    }
  }
}
</script>