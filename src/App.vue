<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <!-- <input type="text" ref="name"> -->
  <!-- <button @click="handleClick">click me</button> -->
  <div v-if="showModal">
    <!-- <Modal :header="header" :text="text" theme="sale" @close="toggleModal" /> : data binds the props to use variables -->
    <Modal theme="sale" @close="toggleModal"> <!-- : data binds the props to use variables -->
      <!-- Add a name slot template -->
      <template v-slot:links>
        <a href="#">sign up</a>
        <a href="#">more info</a>
      </template>
      <!-- Add a default slot template -->
      <h1>Slot modal header</h1>
      <p>slot modal text</p>
    </Modal>
  </div>
  <button @click.alt="toggleModal"> <!-- to add modifier .modifier -->
    open modal (alt)  
  </button>
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
      showModal: false,
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
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    }
  }
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
