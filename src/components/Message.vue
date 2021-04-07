<template>
  <div class="card">
    <div class="card-body">
      <p class="card-text">
        {{ msg }}
      </p>
      <button @click="markAsRead" class="btn btn-primary">Mark as read</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Message",
  props: {
    msg: String,
  },
  methods: {
    markAsRead() {
      console.log(this.msg);
    },
  },
};
</script>