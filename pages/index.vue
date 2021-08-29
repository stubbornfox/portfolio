<template>
  <div class="container">
    <div class="cover">
      <c-flex align="center">
          <c-flex size="100%" align="center" justify="center" height="100vh" flexDirection="column">
            <c-stack is-inline>
              <c-avatar size="2xl" name="Ha Le" class="ha-le wow animate__slideInDown"/>
            </c-stack>
            <c-text text-align="center">
              <c-heading as="h1" :fontSize="['2rem', '2rem','4rem']" :m="['20px']" class="title wow animate__fadeIn">Software Engineer</c-heading>
            </c-text>
            <c-flex align="center" justify="center" class="carosuel" flexDirection="column"  mt="7">
              <Card ref="card1" v-bind:class="{ backward: backward == 1}" :active="currentCard == 1" :cardNumber="cardNumber1" :pos="1" @active-card="update" class="wow animate__slideInUp" @animationend.native="removeAnimateClass"/>
              <EducationCard ref="card2" :active="currentCard == 2" :cardNumber="cardNumber2" :pos="2"  @active-card="update" class="wow animate__fadeInUp"
                @animationend.native="removeAnimateClass" v-bind:class="{ backward: backward == 2}"/>
              <BlogCard ref="card3" :active="currentCard == 3" :cardNumber="cardNumber3" :pos="3"  @active-card="update" class="wow animate__fadeInUp animate__delay-1s"
                @animationend.native="removeAnimateClass" v-bind:class="{ backward: backward == 3}"/>
              <ContactCard ref="card4" :active="currentCard == 4" :cardNumber="cardNumber4" :pos="4" @active-card="update" class="wow animate__fadeInUp animate__delay-1s"
                @animationend.native="removeAnimateClass" v-bind:class="{ backward: backward == 4}"/>
            </c-flex>
          </c-flex>
      </c-flex>
    </div>
    <c-flex :m="['30px auto', '30px auto', '170px auto']" width="100%" justify="center" maxW="5xl" align="center" id="blog-content" :flexDirection="['column', 'column', 'row']">
      <c-box class="blog-content wow animate__fadeInUp" :order="['1', '1', '0', '0']" :m="['20px','20px', '0 40px 0 0']">
        <c-stack spacing="3">
          <c-heading as="h2" :fontSize="['2rem','2rem','4xl','5xl']" fontWeight="700" lineHeight="1">
            Why I want to learn <br/> <span class="pink">Machine Learning</span>
          </c-heading>
          <c-text fontSize="sm" class="gray-500" fontWeight="400">Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages...</c-text>
          <c-button-group size="md"  width="100%" mt="5">
            <c-button rounded="20px" class="bg-red-400" variant-color="red">
              Read more
            </c-button>
            </c-button-group>
        </c-stack>
      </c-box>
      <c-box :order="['0', '0', '1', '1']" :m="['20px','20px', 0, 0]">
        <img src="~/assets/images/blog-min.png" width="600px" class="blog-image" />
      </c-box>
    </c-flex>
    <c-flex class="contact" width="100%" justify="center" id="contact-me">
      <c-flex align="center" maxW="5xl">
        <c-flex align="center" :flexDirection="['column', 'column', 'row']">
          <c-heading as="h2"
            :fontSize="['2rem','2rem','5xl','6xl']"
            :m="['30px','30px', '64px 40px 64px 0']"
            :textAlign="['center', 'center', 'left']"
            class="current-position wow animate__slideInLeft">
            Software Engineer <span class="pink">&</span> Data Scientist
          </c-heading>
          <form class="wow animate__slideInRight" ml="5" name="contact" method="POST" netlify netlify-honeypot="bot-field" action="/thankyou/">
            <c-box  :width="['94%', '400px', '560px']" :p="['20px', '20px', '40px']" m="auto"  class="contact-form">
              <input type="hidden" name="form-name" value="contact" />
              <c-text :fontSize="['2xl','2xl','5xl']" fontWeight="700">Contact me<span class="pink">!</span></c-text>
              <c-stack spacing="3">
                <c-text fontSize="sm" class="gray-500" fontWeight="400">Send me a message then I will reach you as soon as possible</c-text>
                <c-input placeholder="Email" size="md" name="email" />
                <c-input placeholder="Your name" size="md" name="name" />
                <c-input placeholder="Your phone" size="md" name="phone"/>
                <c-textarea placeholder="Write me a message" name="message"/>
                <c-button-group size="md"  width="100%">
                  <c-button class="contact-submit" width="100%" type="submit">
                    Submit
                  </c-button>
                </c-button-group>
              </c-stack>
            </c-box>
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
      update(cardNumber, pos, type) {
        if (type == 'button')
          return
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

