<template>
  <q-page padding>
    <p>Todo Page</p>
  </q-page>
</template>

<script>
  export default {
    data(){
      return {
        tasks: [
          {
            id: 1,
            name: 'Ir al super',
            completed: false
          },
          {
            id: 2,
            name: 'Comprar vasos',
            completed: false
          },
          {
            id: 3,
            name: 'Comprar queso',
            completed: false
          }
        ]
      }
    }
  }
</script>

<style>
  
</style>

