<template>
  <c-box class="page-card" v-bind:class="{ active: active}" @click="activeCard" :cardNumber="cardNumber" :fontSize="['1.5rem','1.5rem', '2rem']" :p="['20px', '20px', '50px 50px 35px']">
    <div class="card-content">
      <span class="gray">Make money from</span>
      <span class="green">coding and investing</span>
      <c-text fontSize="sm" mt="3" mb="3">
        <p  class="gray-pale">
          A dedicated Web Developer who has 5 years experience of ruby on rails 💎, rec dives into  Data Science  for her Majesty ✍️.
          In investing, she strongly believes in the future of cryptocurrency.
        </p>
      </c-text>
      <c-button variant-color="green" rounded="20px"  v-scroll-to="{
     el: '#experience', lazy: false}">Experience & Skills</c-button>
    </div>
  </c-box>
</template>
<script>
  export default {
    props: ['active', 'cardNumber', 'pos'],
    methods: {
      activeCard(event) {
        this.$emit("active-card", this.cardNumber, this.pos, event.target.type);
      }
    }
  }

</script>
