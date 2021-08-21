<template>
  <div class="page-card" v-bind:class="{ active: active}" @click="activeCard" :cardNumber="cardNumber">
    <div class="card-content">
      <c-text fontSize="2xl">
        <span class="gray">Contact</span>
        <span class="orange">Send her an email</span>
      </c-text>
      <c-button variant-color="orange" mb="4"  mt="2" rounded="20px">Call me</c-button>
    </div>
  </div>
</template>
<script>
  export default {
    props: ['active', 'cardNumber', 'pos'],
    methods: {
      activeCard() {
        this.$emit("active-card", this.cardNumber, this.pos);
      }
    }
  }
</script>
