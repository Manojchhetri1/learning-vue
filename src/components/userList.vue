<template>
    <div>
        <h1>User List</h1>
        <ul>
      <li v-for="user in userList" :key="user.id">{{ user.title }}</li>
    </ul>
    </div>
</template>

<script>
import axios from 'axios'
import VueAxios from 'vue-axios'
import { createApp } from 'vue'

const app = createApp({})
app.use(VueAxios,axios)

export default {
    name: 'userList',
    data() {
    return {
      userList: [],
    }
},
    mounted(){
        app.config.globalProperties.$http.get('http://127.0.0.1:8000/api/1/tasks')
        .then((response)=>
        {
            this.userList = response.data.data
            console.warn(response)
        })
    }
}
</script>