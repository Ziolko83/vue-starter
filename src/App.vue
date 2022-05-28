<template>
  <div id="app">
    <h1>Twój e-mail to: {{email}}</h1>
    <div v-if="email.length < 10">Krótki</div>
    <div v-else-if="email.length < 15">OK</div>
    <div class="bad" v-else>Za długi</div>
    <input type="email" v-on:keyup.enter="alertMyEmail" v-model="email">
    <button @click="alertMyEmail()">Wyśwetl email</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: ''
    }
  },
  methods: {
    alertMyEmail() {
      alert(this.email);
    }
  }
}
</script>

<style>
.bad {
  color: red;
}
</style>
