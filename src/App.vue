<template>
<!--  서브밋 기본적인 동작을 막겠다는 뜻임 prevent를 붙이면-->
  <form v-on:submit.prevent="submitForm">
    <div>
      <label for="username">id:</label>
      <input id="username" type="text" v-model="username">
    </div>
    <div>
      <label for="password">pw: </label>
      <input id="password" type="password" v-model="password">
    </div>
    <button type="submit">login</button>
  </form>
</template>
<!--for, id는 한쌍임 포커싱이 자동으로 감-->
<script>
import axios from 'axios'

// 다른곳에서 데이터가 공유되지 않게 써주는 것임.
export default {
  name: 'App',
  data() {
    return {
        username: '',
        password: '', // 문자열
    }
  },
  methods: {
    submitForm() {
      // 폼의 이동, 새로고침 되는 걸 막으려고
      // event.preventDefault()
      console.log(this.username, this.password)
      var url = 'https://jsonplaceholder.typicode.com/users'
      var data = {
        username: this.username,
        password: this.password
      }
      axios.post(url, data)
          .then()
          .catch()
    }
  },
  components: {
  }
}
</script>

<style>
</style>
