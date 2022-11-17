<template>
  <form v-on:submit.prevent="submitForm">
    <div>
      <label for="uName">아이디</label>
      <input id="uName" type="text" v-model="uName">
    </div>
    <button type="submit">btn</button>
  </form>
</template>

<script>
import axios from 'axios';

export default {
  data: function() {
    return {
      uName: ''
    }
  },
  methods: {
    submitForm: function() {

      var url = 'https://jsonplaceholder.typicode.com/users';
      var data = {
        uName: this.uName
      }
      axios.post(url, data)
        .then(function(sss) {
          console.log(sss, "jhkjhkj");
        })
        .catch(function(error) {
          console.log(error);
        })
    }
  }
}
</script>

<style>

</style>