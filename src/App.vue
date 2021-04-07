<template>
  <div class="App">
    <Message v-for="(message, idx) in messages" :key="idx" :msg="message" />
  </div>
</template>

<script>
import Message from "./components/Message.vue";

export default {
  name: "App",
  components: {
    Message,
  },
  data() {
    return {
      messages: ["first", "second", "third"],
    };
  },
  mounted() {
    setInterval(() => {
      fetch("http://localhost:8000")
        .then((res) => res.text())
        .then((text) => this.messages.push(text));
    }, 1000);
  },
};
</script>

<style>
.App {
  padding: 60px;
  display: grid;
  row-gap: 20px;
}
</style>