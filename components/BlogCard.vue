<template>
  <c-box v-bind:class="{ active: active}" @click="activeCard" :cardNumber="cardNumber" :fontSize="['1.5rem','1.5rem', '2rem']"
    :p="['20px', '20px', '50px 50px 35px']">
    <c-box class="card-content" textAlign="center">
      <span class="gray">Blog</span>
      <span class="pink">ML & Web Application</span>
      <c-text fontSize="sm" mt="3" mb="3">
        <p  class="gray-pale">
          The place I share my knowledge and my current interests in ML and SE, Why should I need to know both ML and SE.
        </p>
      </c-text>
      <c-button class="bg-red-400" rounded="20px" v-scroll-to="{
     el: '#blog-content', offset: -200, lazy: false}">Start Reading</c-button>
    </c-box>
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
