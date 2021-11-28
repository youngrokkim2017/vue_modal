<template>
  <h1>{{ title }}</h1>
  <!-- <input type="text" ref="name"> -->
  <!-- <button @click="handleClick">click me</button> -->
  <Modal :header="header" :text="text" theme="sale" /> <!-- : data binds the props to use variables -->
</template>

<script>
// import components
import Modal from "./components/Modal"

// root component
export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'my first vue app',
      header: 'vue props header',
      text: 'add some text props',
    }
  },
  // methods: {
  //   // handleClick() {
  //   //   // use refs to get dom elements
  //   //   // console.log(this.$refs.name)
  //   //   // this.$refs.name.classList.add('active')
  //   //   this.$refs.name.focus()
  //   // }
  // }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
