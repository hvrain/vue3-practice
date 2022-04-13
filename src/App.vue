<template>
  <h1 @click="increase">
    {{ count }} / {{ doubleCount }}
  </h1>
  <h1 @click="changeMessage">
    {{ message }} / {{ reversedMessage }}
  </h1>
</template>

<script>
export default {
  data() {
    return {
      count: 0,
      message: "Hello World!"
    }
  },
  computed: {
    doubleCount() {
      return this.count * 2
    },
    reversedMessage() {
      return this.message.split("").reverse().join("")
    }
  },
  watch: {
    message(value) {
      console.log(value)
    }
  },
  created() {
    console.log("count:",this.doubleCount)
  },
  mounted() {
    console.log("message:",this.message)
  },
  methods: {
    increase() {
      this.count += 1
    },  
    changeMessage() {
      this.message = 'Good!'
    }
  }
}
</script>