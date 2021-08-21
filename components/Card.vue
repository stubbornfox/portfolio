<template>
  <div class="page-card" v-bind:class="{ active: active}" @click="activeCard" :cardNumber="cardNumber">
    <div class="card-content">
      <span class="gray">Make money from</span>
      <span class="green">coding and investing</span>
      <c-text fontSize="sm" mt="3" mb="3">
        <p  class="gray-pale">
          A dedicated Web Developer who has 5 years experience of ruby on rails 💎, this person also dives into  Data Science  for her Majesty ✍️.
        </p>
      </c-text>
      <c-button variant-color="green" rounded="20px">Experience & Skills</c-button>
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
