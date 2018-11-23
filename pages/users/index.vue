<template>
  <section class="users">
    <User
      v-for="user in users"
      :key="user.id"
      thumbnail="https://www.w3schools.com/w3css/img_avatar3.png"
      :name="user.name"
      :email="user.email"
      :id="user.id"/>
  </section>
</template>

<script>
import User from '@/components/User'
import axios from 'axios'
export default {
  components: {
    User
  },
  title: '',
  async asyncData () {
    const {data} = await axios.get('https://jsonplaceholder.typicode.com/users')
    return {users:data}
  }
};
</script>

<style scoped>
.users-header {

}
.users {
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
  align-items: center;
}
</style>
