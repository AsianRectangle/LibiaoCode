<script setup>
import { ref } from 'vue'
import axios from 'axios'
defineProps({
  msg: String,
})
const axiosInstance = axios.create({
  baseURL: 'http://192.168.0.229/api',
  timeout: 5000,
})

const login = async () => {
  const res = await axiosInstance({url:"/authority/login",
  method:"post",
  data:{
    "account":"AsianRectangle",
    "password":"Lele060321"
}}
)
console.log(res)
  return res.data
}
const count = ref(0)


axiosInstance.post('/user', {
    firstName: 'Chengle',
    lastName: 'Qian'
  },)
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  });

</script>


<template>
  <h1>{{ msg }}</h1>
  <input type="text" id="fName" placeholder="Enter your First Name">
  <input type="text" id="lName" placeholder="Enter your Last Name">

  <div class="card">
    <button type="button" @click="login">Login</button>
    <p>
      Edit
      <code>components/HelloWorld.vue</code> to test HMR
    </p>
  </div>

  <p>
    Check out
    <a href="https://vuejs.org/guide/quick-start.html#local" target="_blank"
      >create-vue</a
    >, the official Vue + Vite starter. Hellooooo
  </p>
  <p>
    Install
    <a href="https://github.com/vuejs/language-tools" target="_blank">Volar</a>
    in your IDE for a better DX
  </p>
  <p class="read-the-docs">Click on the Vite and Vue logos to learn more</p>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
