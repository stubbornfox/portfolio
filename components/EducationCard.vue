<template>
  <c-box class="page-card" v-bind:class="{ active: active}" @click="activeCard" :cardNumber="cardNumber" :fontSize="['1.5rem','1.5rem', '2rem']">
    <div class="card-content">
      <span class="gray">Almost Master in</span>
      <span class="orange">Computer Science</span>
      <img src="~assets/images/hero1.svg" width="120">
      <c-button variant-color="orange" mb="4"  mt="2" rounded="20px">Education</c-button>
    </div>
  </c-box>
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
