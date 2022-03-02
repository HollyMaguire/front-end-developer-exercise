<template>
      <b-card id="card" @click="selectPlan()"
      :header="name"
      :border-variant="borderVariant"
      :header-bg-variant="borderVariant"
      :header-text-variant="textVariant"
      header-tag="header"
      :title=priceString
      v-bind:class="{ chosenPlan: isChosenPlan }"
      
    >
     <b-card-text>
           <div v-for="feature in this.features" :key="feature">
            {{feature}}
          <br>
            </div>
       </b-card-text>
      <b-button href="#" :variant="buttonVariant">{{buttonText}}</b-button>
    </b-card>  
</template>

<script>
export default {
  name: 'PricingCard',
  props: {name: String, price: Number, userLimit: Number, storage: Number, support: String, buttonText: String, features: Array, paid: Boolean},
  computed: {
    priceString: function() { return "$"+this.price+"/mo"},
    isChosenPlan: function() { return (this.name == this.$store.state.chosenPlan) },
    borderVariant: function() { return (this.isChosenPlan ? "primary" : "null") },
    textVariant: function() { return (this.isChosenPlan ? "white" : "black") },
    buttonVariant: function() { return(this.paid == true ? "primary" : "white") }
    // variant: function() {return (this.name ==this.$store.free ? "white" : "primary")}
    },
  methods: {
    selectPlan() {
      this.$store.commit("selectPlan", this.name);
    }
  }
};
</script>
