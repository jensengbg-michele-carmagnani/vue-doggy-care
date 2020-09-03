<template>
  <section id="home">
    <h2>Wellcome to Doggy daycare</h2>
    <p>We are currently taking care of {{dogs.length}}</p>
  </section>
</template>

<script>
export default {
  name:'Home',
  props: {
    dogs:Array
  }
}
</script>

<style>

</style>