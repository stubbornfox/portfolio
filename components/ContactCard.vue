<template>
  <div class="page-card contact-card" v-bind:class="{ active: active}" @click="activeCard" :cardNumber="cardNumber">
    <div class="card-content">
      <c-text fontSize="2rem" class="pink" lineHeight="1">
        Let's talk :)
      </c-text>
      <c-button variant-color="red" rounded="20px" v-scroll-to="'#contact-me'" mt=5  variant="solid">Contact</c-button>
    </div>
  </div>
</template>
<script>
  export default {
    props: ['active', 'cardNumber', 'pos'],
    methods: {
      activeCard(event) {
        this.$emit("active-card", this.cardNumber, this.pos, event.target.type);
      },
    }
  }
</script>
