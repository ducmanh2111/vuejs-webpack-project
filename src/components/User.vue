<template>
  <div class="user">
    <p>{{ user.email }}</p>
    <button
      class="delete"
      @click="handleDelete($event)"
      > Delete </button>
  </div>
</template>

<script>

export default {
  name: 'user',
  props: {
    user: {
      type: Object,
      default: null
    }
  },
  data() {
    return {
    }
  },
  methods: {
    handleDelete(e) {
      var data = {
        id: this.user.id
      }
      // console.log("HandleDelete User.vue");
      this.$emit("deleteUser", data)
    }
  }
}
</script>

<style>
  .user {
    position: relative;
  }

  .user .delete {
    position: absolute;
    top: 0;
    right: 0
  }
</style>