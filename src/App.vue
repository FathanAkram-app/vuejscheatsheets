
<template>

  <h1>{{ title }}</h1>
  <div v-if="showModal">
    <ModalComponent :header="header" :textContent="textContent" theme="sale" @close="toggleModal"/>
  </div>
  <button @click="toggleModal">Open Modal</button>
  
</template>

<script>
import ModalComponent  from "./components/ModalComponent.vue";
export default {
  components: {
    ModalComponent
  },
  name: 'App',
  data(){
    return {
      title: 'My First Vue App.',
      header: 'Modal Component',
      textContent: 'this what it looks like for the text of the modal component',
      showModal: false
    }
  },
  methods:{
    handleClick(){
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    },
    toggleModal(){
      this.showModal = !this.showModal
    }
  },
  
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

h1{
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
