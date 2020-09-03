<template>
  <section id="doginfo">
    <figure>
      <img :src="dog.img" :alt="dog.name" />
    </figure>
    <aside class="info">
      <h1>{{ dog.name }}</h1>
      <section>
        <p>Breed &#8594; <b> {{ dog.breed }}</b></p>
        <p>Chip number &#8594;<b>{{ dog.chipNumber }}</b></p>
      </section>
      <section>
        <p>Owner &#8594;<b>{{ dog.owner.name }}</b></p>
        <p>phoneNuber &#8594; <b>{{ dog.owner.phoneNumber }}</b></p>
      </section>
    </aside>
  </section>
</template>

<script>
export default {
  name: "DogInfo",
  props: {
    dogs: Array,
  },
  computed: {
    dog() {
      console.log(this.dogs);
      return this.dogs.filter(
        (dog) => dog.chipNumber === this.$route.params.chipNumber
      )[0];
    },
  },
};
</script>

<style lang="scss">
#doginfo {
  display: flex;
  justify-content: space-around;
align-items: center;

  figure {
    margin: 0;
    padding: 0;
    grid-column: auto / span 1;
    grid-row: auto / span 3;
    display: flex;
    justify-content: center;
    align-items: center;
    

    img {
      width: 12rem;
      height: 12rem;
      object-fit: cover;
      border: 3px rgb(75, 207, 135) solid;
      border-radius: 999rem;
      
    }
  }

  h1 {
    grid-column: auto / span 2;
    font-size: 3rem;
    margin: 0;
    padding: 0;
    display: flex;
    align-items: flex-end;
    
  }

  .info {
    display: flex;
    flex-direction: column;
    align-items:space-around;
    justify-content: space-around;
    
    border: 1px dotted black;
    padding: 1rem;
    border-radius: 1rem;
    background: white;

    > section {
       width: 100%;
       display: flex;
        flex-direction: column;
       align-items: flex-start;
       
              

      h2 {
        margin: 0;
        padding: 0;
        font-weight: 400;
      }
    }
  }
}
</style>
