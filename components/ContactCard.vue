<template>
  <c-box class="page-card contact-card" v-bind:class="{ active: active}" @click="activeCard" :cardNumber="cardNumber" :fontSize="['1.5rem','1.5rem', '2rem']">
    <div class="card-content">
      <c-text class="pink" lineHeight="1">
        Let's talk :)
      </c-text>
      <c-button variant-color="red" rounded="20px" v-scroll-to="'#contact-me'" mt=5  variant="solid">Contact</c-button>
    </div>
  </c-box>
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
