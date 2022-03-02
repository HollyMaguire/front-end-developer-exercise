<template>
  <b-container class="text-center">
    <b-row>
      <b-col class="mt-5">
        <h1>Pricing</h1>
      </b-col>
    </b-row>
    <b-row class="justify-content-center">
      <b-col md="8">
        <p>
          Lorem ipsum dolor sit amet consectetur, adipisicing elit. Explicabo,
          tenetur. Eius, fugit quidem tempore, quia officia impedit possimus
          officiis doloremque autem illum reiciendis libero dignissimos
          repellendus dolores veniam error odit!
        </p>
      </b-col>
    </b-row>
  <div>
  <b-card-group deck class="justify-content-center">
    <div v-for="option in this.$store.state.pricingOptions" :key="option.name">
    <PricingCard :features=option.features :price=option.cost :name=option.name :buttonText=option.cta :paid=option.paid ></PricingCard>
    </div>
    
  </b-card-group>
  
</div>
  </b-container>
  
  
  
</template>

<script>
export default {
  name: 'Pricing',
  layout: 'default',
  computed: {},
};
</script>

<style lang="scss" scoped>
p {
  color: #6c757d;
  font-size: 1.25rem;
}

</style>
