<template>
  <div class="container">
    <div class="cover">
      <c-flex align="center">
        <c-flex size="100%" align="center" justify="center" height="100vh" flexDirection="column">
          <c-text text-align="center">
            <c-heading as='h1' class="title wow animate__fadeIn">Thank you very much</c-heading>
          </c-text>
          <c-text fontSize="md" class="gray-500" fontWeight="600" text-align="center" bg="white">
            It's amazing that you give me a chocolate! Have a nice day.
            <c-text class="pink" fontWeight="600" fontSize="md">
             <NuxtLink to="/">🏠 Go Home</NuxtLink>
          </c-text>
          </c-text>
        </c-flex>
      </c-flex>
    </div>
  </div>
</template>

<script>
  if (process.browser) { // Here we introduce... According to the environment wow.js
    var {WOW} = require('wowjs')
  }

  export default {
    mounted() {
      this.$nextTick((tep) => {
        if (process.browser) { // On the page mounted In the life cycle Instantiate according to the environment WOW
          new WOW({animateClass: 'animate__animated'}).init()
        }
      });
    },
  }
</script>
