<template>
  <c-box v-bind:class="{ active: active}" @click="activeCard" :cardNumber="cardNumber" :fontSize="['1.5rem','1.5rem', '2rem']" :p="['20px', '20px', '50px 50px 35px']">
    <div class="card-content">
      <span class="gray">Almost Master in</span>
      <span class="green">Computer Science</span>
      <img src="~assets/images/hero1.svg" style="height: 75px">
      <c-button variant-color="green" mb="4"  mt="2" rounded="20px"v-scroll-to="{
     el: '#education', offset: 0, lazy: false}">Education</c-button>
    </div>
  </c-box>
</template>
<script>
  export default {
    props: ['active', 'cardNumber', 'pos'],
    methods: {
      activeCard() {
        this.$emit("active-card", this.cardNumber, this.pos, event.target.type);
      }
    }
  }
</script>
