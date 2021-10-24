<template>
  <form>
    <label>Email:</label>
    <input type="email" required v-model="email">

    <input type="checkbox" required>
    <label>Accept terms and conditions</label>
  </form>
  <p>Email: {{ email }}</p>
</template>

<script>
export default {
  data () {
    return {
      email: null
    }
  }
}
</script>
