<template>
  <div class="container">
    <div class="cover">
      <c-flex align="center">
          <c-flex size="100%" align="center" justify="center" height="100vh" flexDirection="column">
            <c-stack is-inline>
              <c-avatar size="2xl" name="Ha Le" class="ha-le wow animate__slideInDown"/>
            </c-stack>
            <c-text text-align="center">
              <h1 class="title wow animate__fadeIn">Software Engineer</h1>
            </c-text>
            <c-flex align="center" justify="center" class="carosuel" flexDirection="column"  mt="7">
              <Card ref="card1" v-bind:class="{ backward: backward == 1}" :active="currentCard == 1" :cardNumber="cardNumber1" :pos="1" @active-card="update" class="wow animate__slideInUp" @animationend.native="removeAnimateClass"/>
              <EducationCard ref="card2" :active="currentCard == 2" :cardNumber="cardNumber2" :pos="2"  @active-card="update" class="wow animate__fadeInUp"
                @animationend.native="removeAnimateClass" v-bind:class="{ backward: backward == 2}"/>
              <BlogCard ref="card3" :active="currentCard == 3" :cardNumber="cardNumber3" :pos="3"  @active-card="update" class="wow animate__fadeInUp animate__delay-1s"
                @animationend.native="removeAnimateClass" v-bind:class="{ backward: backward == 3}"/>
              <ContactCard ref="card4" :active="currentCard == 4" :cardNumber="cardNumber4" :pos="4"  @active-card="update" class="wow animate__fadeInUp animate__delay-1s"
                @animationend.native="removeAnimateClass" v-bind:class="{ backward: backward == 4}"/>
            </c-flex>
          </c-flex>
      </c-flex>
    </div>
    <c-flex class="blog" width="100%" justify="center" maxW="5xl" align="center">
      <div class="blog-content wow animate__fadeInUp">
        <c-stack spacing="3">
          <c-text fontSize="5xl" fontWeight="700" lineHeight="1">
            Why I want to learn  <span class="pink">Machine Learning</span>
          </c-text>
          <c-text fontSize="sm" class="gray-500" fontWeight="400">Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages...</c-text>
          <c-button-group size="md"  width="100%" mt="5">
              <c-button rounded="20px" class="bg-red-400" variant-color="red">
                Read more
              </c-button>
              <c-link s="router-link" to="/" color="teal.500">Discover my blogs</c-link>
              </c-button-group>
        </c-stack>
      </div>
      <div class="blog-image">
        <img src="~/assets/images/blog-min.png" width="600px" />
      </div>
    </c-flex>
    <c-flex class="contact" width="100%" justify="center">
      <c-flex align="center" maxW="5xl">
        <c-flex align="center">
          <div class="current-position wow animate__slideInLeft">
            Software Developer <span class="pink">&</span> Data Scientist
          </div>
          <form class="contact-form wow animate__slideInRight" ml="5" name="contact" method="POST" data-netlify="true" data-netlify-honeypot="bot-field">
            <c-text fontSize="5xl" fontWeight="700">Contact me<span class="pink">!</span></c-text>
            <c-stack spacing="3">
              <c-text fontSize="sm" class="gray-500" fontWeight="400">Send me a message then I will reach you as soon as possible</c-text>
              <input type="hidden" name="form-name" value="contact" />
              <c-input placeholder="Email" size="md" />
              <c-input placeholder="Your name" size="md" />
              <c-input placeholder="Your phone" size="md" />
              <c-textarea placeholder="Write me a message" />
              <c-button-group size="md"  width="100%">
                <c-button class="contact-submit" width="100%" type="submit">
                  Submit
                </c-button>
              </c-button-group>
            </c-stack>
          </form>
        </c-flex>
      </c-flex>
    </c-flex>
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
    data() {
      return {
        backward: 0,
        currentCard: 1,
        cardNumber1: 1,
        cardNumber2: 2,
        cardNumber3: 3,
        cardNumber4: 4,
      }
    },
    methods: {
      removeAnimateClass(animateEvent){
        animateEvent.target.classList.remove('animate__animated', 'animate__slideInUp', 'animate__fadeInUp', 'wow', 'animate__delay-1s');
      },
      update(cardNumber, pos) {
        this.currentCard = pos
        this.cardNumber1 -= 1
        this.cardNumber2 -= 1
        this.cardNumber3 -= 1
        this.cardNumber4 -= 1

        if(this.cardNumber1 == 0) {
          this.cardNumber1 = 4
          this.backward = 1
        }

        if(this.cardNumber2 == 0) {
          this.cardNumber2 = 4
          this.backward = 2
        }

        if(this.cardNumber3 == 0) {
          this.cardNumber3 = 4
          this.backward = 3
        }
        if(this.cardNumber4 == 0) {
          this.cardNumber4 = 4
          this.backward = 4
        }
      }
    }
};
</script>

