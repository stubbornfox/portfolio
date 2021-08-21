<template>
  <div class="page-card" v-bind:class="{ active: active}" @click="activeCard" :cardNumber="cardNumber">
    <div class="card-content">
      <span class="gray">Blog</span>
      <span class="pink">ML & Web Application</span>
      <c-text fontSize="sm" mt="3" mb="3">
        <p  class="gray-pale">
          Raising sentiments in web development with ruby on rails, tutorials of machine learning, how good to know both ML and SE.
        </p>
      </c-text>
      <c-button class="bg-red-400" rounded="20px">Start Reading</c-button>
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
