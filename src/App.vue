<template>
  <div>
    <Navbar />
    <Sidebar />
    <Table />
  </div>
</template>


<script>
import Navbar from './components/Nav_Bar.vue'
import Sidebar from './components/Side_Bar.vue'
import Table from './components/Table-component.vue'


export default {
  name: 'App',
  components: {
    Navbar,
    Sidebar,
    Table
}
}
</script>

<style>
body{
  margin: 0%;
  background: grey;
}
</style>
