<template>
  <section class="single-user">
  <div class="top">
    <h1>{{ name }}</h1>
  </div>
    <div>
    <a class="img" href="">
      <div class="img__overlay"></div>
      <img src="https://www.w3schools.com/w3css/img_avatar3.png"/>
    </a>
    </div>

    <label class="first">Username</label>
    <p>{{ username }}</p>
    <label>Email</label>
    <p>{{ email }}</p>
    <label>Address</label>
    <p>{{ address.street + ' ' + address.suite + ' ' + address.city}}</p>
    <p>{{ address.zipcode + ' ' + address.geo.lat + ' ' + address.geo.lng }}</p>
    <label>Phone</label>
    <p>{{ phone }}</p>
    <label>Website</label>
    <p>{{ website }}</p>
    <label>Company</label>
    <p>{{ company.name}}</p>
    <p>{{ company.catchPhrase }}</p>
    <p>{{ company.bs }}</p>
  </section>
</template>

<script>
import axios from 'axios'

export default {
  validate ({ params }) {
    return !isNaN(+params.id)
  },
  async asyncData({params, error}){
    const {data} = await axios.get(`https://jsonplaceholder.typicode.com/users/${+params.id}`)
    return data
  }
}

</script>

<style scoped>
.first {
  margin-top: 10px;
}
label {
  font-weight: bolder;
}
h1 {
  text-transform: uppercase;
  margin-top: 20px;
  color: #342d34;
}
.top {
  width: 100%;
  height: 230px;
  background-color: #36d290;
  index: 1;
  position: relative;
}
.img {
  border-radius: 100%;
  display: flex;
  flex: 0 0 150px;
  height: 250px;
  justify-content: center;
  overflow: hidden;
  position: relative;
  width: 250px;
  margin-top: -150px;
}
.img img {
  height: 100%;
}
.img__overlay {
  align-items: center;
  bottom: 0;
  display: flex;
  justify-content: center;
  left: 0;
  opacity: 0;
  position: absolute;
  right: 0;
  top: 0;
  transition: opacity 0.25s;
  z-index: 2;
}
.img__overlay:hover {
  opacity: 2;
}
.img__overlay {
  background-color: rgba(46,204,113,0.4);
  background: linear-gradient(65deg, rgba(46,204,113,0.4), rgba(243,156,18,0.4));
  color: #fafafa;
  font-size: 24px;
}
.single-user {
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 15px;
  width: 500px;
  height: 100%;
  box-sizing: border-box;
  padding: 8px;
  border: 1px solid #ccc;
  box-shadow: 0 2px 2px #aaa;
  margin: 10px;
}
</style>
