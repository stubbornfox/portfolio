<template>
  <div class="container">
    <c-text as="h1" fontSize="0">Le Thi Nhi Ha</c-text>
    <c-text as="h1" fontSize="0">Ha Le Twente</c-text>
    <c-text as="h1" fontSize="0">Ha Le Software Engineer</c-text>
    <c-box class="cover" :p="['50px 0', '50px 0', 'unset']">
      <c-flex align="center">
          <c-flex size="100%" align="center" justify="center" minH="100vh" flexDirection="column">
            <c-avatar size="xl" name="Ha Le" class="ha-le wow animate__fadeIn"/>
            <c-flex>
              <c-text text-align="center">
                <c-heading as="h2" :fontSize="['2.5rem', '2.5rem','4rem']" :m="['20px']" class="title wow animate__fadeInDown">Software & ML Engineer</c-heading>
              </c-text>
            </c-flex>
            <c-box v-show="!expanded" width="100%">
              <c-flex align="center" justify="center" class="carosuel" flexDirection="column"  mt="7" mx="auto" position="relative">
                <Card ref="card1" v-bind:class="{ backward: backward == 1}" :active="currentCard == 1" :cardNumber="cardNumber1" :pos="1" @active-card="update" class="wow animate__slideInUp page-card" @animationend.native="removeAnimateClass"/>
                <EducationCard ref="card2" :active="currentCard == 2" :cardNumber="cardNumber2" :pos="2"  @active-card="update" class="wow animate__fadeInUp page-card"
                  @animationend.native="removeAnimateClass" v-bind:class="{ backward: backward == 2}"/>
                <BlogCard ref="card3" :active="currentCard == 3" :cardNumber="cardNumber3" :pos="3"  @active-card="update" class="wow animate__fadeInUp page-card"
                  @animationend.native="removeAnimateClass" v-bind:class="{ backward: backward == 3}"/>
                <ContactCard ref="card4" :active="currentCard == 4" :cardNumber="cardNumber4" :pos="4" @active-card="update" class="wow animate__fadeInUp page-card"
                  @animationend.native="removeAnimateClass" v-bind:class="{ backward: backward == 4}"/>
              </c-flex>
            </c-box>
            <c-box width="100%" v-show="expanded">
              <c-flex flexWrap="wrap" align="center" justify="center" flexDirection="row"  mx="auto" maxW="1200px" pos="relative">
                <Card class="lg-page-card wow animate__fadeIn"/>
                <EducationCard class="lg-page-card wow animate__fadeIn"/>
                <BlogCard class="wow animate__fadeIn lg-page-card"/>
                <ContactCard  class="wow animate__fadeIn lg-page-card"/>
              </c-flex>
            </c-box>
          </c-flex>
      </c-flex>
    </c-box>
    <c-box  bg="white">
      <c-flex :p="['50px 20px', '50px 20px', '100px 40px']" maxW="1024px" m="0 auto" :flexDirection="['column', 'column', 'row']" id="experience">
        <c-stack :pr="[0, 0, '20px']" spacing="8">
          <c-heading as="h2" :fontSize="['2rem','2rem','4xl','5xl']" class="green">Experience</c-heading>
          <c-stack :spacing="5">
            <c-stack :spacing="2" class="experience-card wow animate__slideInUp">
              <c-box>
                <c-flex align="center">
                  <c-link href="https://www.eastagile.com/" target="_blank">
                    <img src="~/assets/images/eastagile.png" class="company-logo" style="width:70px" />
                  </c-link>
                  <c-box>
                    <c-box fontSize="1.125rem" fontWeight="600" class="gray"> Senior Software Developer at East Agile</c-box>
                    <c-box fontSize="sm" class="gray-500">2015-2019</c-box>
                  </c-box>
                </c-flex>
              </c-box>
              <c-box fontSize="sm" class="gray-500">
                <c-text mt="10px">Ruby on Rails Developer - Develop Web applications:</c-text>
                <c-list spacing="1"  as="ol" ml="5px">
                  <c-list-item>
                    <c-list-icon icon="check-circle" color="green.500" />
                    <c-link color="green.500" href="https://www.thestorefront.com/" target="_blank">
                      The storefront
                    </c-link>
                     - Space Renting app
                  </c-list-item>
                  <c-list-item>
                     <c-list-icon icon="check-circle" color="green.500" />
                    <c-link color="green.500" href="https://www.applyflow.com/" target="_blank">
                      Applyflow
                    </c-link>
                    - Recruitment platform
                  </c-list-item>
                  <c-list-item>
                     <c-list-icon icon="check-circle" color="green.500" />
                    <c-link color="green.500" href="https://www.clistudios.com/" target="_blank">
                      CLI Studios
                    </c-link>
                      - Online Dance Teaching platform
                  </c-list-item>
                </c-list>
              </c-box>
            </c-stack>
            <c-stack :spacing="2" class="experience-card wow animate__slideInUp">
              <c-box>
                <c-flex align="center">
                  <c-link href="https://www.fpt-software.com/" target="_blank">
                    <img src="~/assets/images/fpt-software.jpeg" class="company-logo"/>
                  </c-link>
                  <c-box>
                    <c-box fontSize="1.125rem" fontWeight="600" class="gray"> Junior Software Developer at FPT</c-box>
                    <c-box fontSize="sm" class="gray-500">2014-2015</c-box>
                  </c-box>
                </c-flex>
              </c-box>
              <c-box fontSize="sm" class="gray-500">ASP.Net Developer - Develop internal software for PETRONAS Digital Sdn Bhd - Malaysia</c-box>
            </c-stack>
            <c-stack :spacing="2" class="experience-card wow animate__slideInUp">
              <c-box>
                <c-flex align="center">
                  <c-link href="https://www.gameloft-sea.com/" target="_blank">
                    <img src="~/assets/images/gameloft.png" class="company-logo"/>
                  </c-link>
                  <c-box>
                    <c-box fontSize="1.125rem" fontWeight="600" class="gray"> Junior Game Developer at Gameloft</c-box>
                    <c-box fontSize="sm" class="gray-500">2013-2014</c-box>
                  </c-box>
                </c-flex>
              </c-box>
              <c-box fontSize="sm" class="gray-500" mt="10px">Java Developer - Develop "Heroes of Order & Chaos" game</c-box>
            </c-stack>
          </c-stack>
          </c-stack>
        </c-stack>
        </c-stack>
        <c-divider orientation="vertical" />
        <c-stack :pl="[0, 0, '20px']" :pt="['40px', '40px', 0]" flexGrow="1" spacing="8" >
          <c-heading  as="h2" :fontSize="['2rem','2rem','4xl','5xl']" class="green">Skills</c-heading>
          <c-stack spacing="5">
            <c-heading fontSize="1.125rem" fontWeight="600" class="gray">Web Application</c-heading>
            <c-flex>
              <c-flex justify="center" flexDirection="column" align="center"  mr="10px">
                <c-circular-progress :value="100" color="green" size="60px" :thickness="0.1" class="wow animate__fadeIn">
                  <c-circular-progress-label>
                    RoR
                  </c-circular-progress-label>
                </c-circular-progress>
                <c-text color="gray.500" fontSize="sm"><span style="font-weight: bold;">4</span> yrs+</c-text>
              </c-flex>
              <c-flex justify="center" flexDirection="column" align="center"  mr="10px">
                <c-circular-progress :value="100" color="green" size="60px" :thickness="0.1" class="wow animate__fadeIn">
                  <c-circular-progress-label>
                    HTML
                  </c-circular-progress-label>
                </c-circular-progress>
                 <c-text color="gray.500" fontSize="sm"><span style="font-weight: bold;">5</span> yrs+</c-text>
              </c-flex>
              <c-flex justify="center" flexDirection="column" align="center"  mr="10px">
                <c-circular-progress :value="100" color="green" size="60px" :thickness="0.1" class="wow animate__fadeIn">
                  <c-circular-progress-label>
                    JS
                  </c-circular-progress-label>
                </c-circular-progress>
                 <c-text color="gray.500" fontSize="sm"><span style="font-weight: bold;">5</span> yrs+</c-text>
              </c-flex>
              <c-flex justify="center" flexDirection="column" align="center"  mr="10px">
                <c-circular-progress :value="100" color="green" size="60px" :thickness="0.1" class="wow animate__fadeIn">
                  <c-circular-progress-label>
                    CSS
                  </c-circular-progress-label>
                </c-circular-progress>
                <c-text color="gray.500" fontSize="sm"><span style="font-weight: bold;">5</span> yrs+</c-text>
              </c-flex>
            </c-flex>
            <c-divider />
            <c-heading fontSize="1.125rem" fontWeight="600" class="gray">Machine Learning</c-heading>
            <c-flex>
              <c-flex justify="center" flexDirection="column" align="center" mr="10px">
                <c-circular-progress :value="100" color="green" size="60px" :thickness="0.1" class="wow animate__fadeIn">
                  <c-circular-progress-label>
                    Python
                  </c-circular-progress-label>
                </c-circular-progress>
                <c-text color="gray.500" fontSize="sm"><span style="font-weight: bold;">9</span> mths+</c-text>
              </c-flex>
              <c-flex justify="center" flexDirection="column" align="center">
                <c-circular-progress :value="100" color="green" size="60px" :thickness="0.1" class="wow animate__fadeIn">
                  <c-circular-progress-label align="center">
                    Spark ML
                  </c-circular-progress-label>
                </c-circular-progress>
                <c-text color="gray.500" fontSize="sm"><span style="font-weight: bold;">2</span> mths</c-text>
              </c-flex>
            </c-flex>
            <c-divider />
            <Social class="gray-500"/>
          </c-stack>
        </c-stack>
      </c-flex>
    </c-box>
    <c-flex id="education" align="center" flexDirection="column" :p="['50px 20px', '50px 20px', '100px 20px']">
      <c-heading align="center" as="h2" :fontSize="['2rem','2rem','4xl','5xl']" fontWeight="700" lineHeight="1" m="20px 0 60px" class="wow animate__fadeIn">
        <span class="green">Education Background</span>
      </c-heading>
      <div class="education-bg"></div>
      <c-flex align-items="center" :flexDirection="['column', 'column', 'row']">
        <c-stack :mr="[0, 0, '60px']" :mb="['40px', '40px', 0]">
            <script src="https://unpkg.com/@lottiefiles/lottie-player@latest/dist/lottie-player.js"></script>
              <c-box>
                <lottie-player src="https://assets7.lottiefiles.com/packages/lf20_K7aZUG.json"  background="transparent"  speed="1"  style="width: 300px; height: 300px;" loop autoplay>
                </lottie-player>
            </c-box>
          </c-stack>
        <c-box class='education-content'>
           <p>
            <c-flex class="wow animate__slideInLeft">
              <c-avatar size="xl" name="UT" class="twente" borderRadius="md"/>
              <c-box ml="3">
                <c-box color="gray">University of Twente - Master Computer Science</c-box>
                <c-box>-</c-box>
                <c-box color="var(--gray-500)">2020-2022</c-box>
              </c-box>
            </c-flex>
          </p>
          <p>
            <c-flex  class="wow animate__slideInRight">
            <c-avatar size="xl" name="FPT" class="fpt" borderRadius="md"/>
             <c-box ml="3">
              <c-box >FPT University - Bachelor Software Engineering</c-box>
              <c-box>7.78</c-box>
              <c-box color="var(--gray-500)">2010-2014</c-box>
            </c-box>
          </c-flex>
          </p>
          <p>
            <c-flex  class="wow animate__slideInLeft">
              <c-avatar size="xl" name="LQD" class="lqd" borderRadius="md"/>
             <c-box ml="3">
              <c-box >Lê Quý Đôn High School for the Gifted, Quang Tri</c-box>
              <c-box color="var(--gray-500)">2007-2010</c-box>
              </c-box>
            </c-flex>
          </p>
        </c-box>
      </c-flex>
    </c-flex>
    <c-flex :m="['30px auto', '30px auto', '170px auto']" width="100%" justify="center" maxW="5xl" align="center" id="blog-content" :flexDirection="['column', 'column', 'row']">
      <c-box class="blog-content wow animate__fadeInUp" :order="['1', '1', '0', '0']" :m="['20px','20px', '0 40px 0 0']">
        <c-stack spacing="3">
          <c-heading as="h2" :fontSize="['2rem','2rem','4xl','5xl']" fontWeight="700" lineHeight="1">
            Why I want to learn <br/> <span class="pink">Machine Learning</span>
          </c-heading>
          <c-text fontSize="sm" class="gray-500" fontWeight="400">While working on building an online dance studio application, the studio owner wants to improve the system by recommending the listing of videos that suits user's demands. In order to implement this requirement, we have used an opensource prediction platform called PredictionIO. Without any knowledge on machine learning, everything is literally a black box, blind and difficult. The vague understanding has urged me to dive into the field to able to know the magic behind the ML model… </c-text>
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
    <c-flex class="contact" width="100%" justify="center" id="contact-me" :pb="['40px', '40px', '20px', 0]">
      <c-flex align="center" maxW="5xl" flexGrow="1">
        <c-flex align="center" :flexDirection="['column', 'column', 'column', 'row']" flexGrow="1" mx="auto">
          <c-heading as="h2"
            :fontSize="['2rem','2rem','5xl','6xl']"
            :m="['20px','20px', '20px','64px 40px 64px 0']"
            :textAlign="['center', 'center', 'left']"
            class="current-position wow animate__slideInLeft">
            Software Engineer <span class="pink">&</span> <br/>Data Scientist
          </c-heading>
          <form class="wow animate__slideInRight" style="width: 100%" name="contact" method="POST" netlify netlify-honeypot="bot-field" action="/thankyou/">
            <c-box  :width="['unset', '400px', '400px', '560px']" :p="['20px', '20px', '40px']"  class="contact-form" mx="20px">
              <input type="hidden" name="form-name" value="contact" />
              <c-text :fontSize="['2xl','2xl','5xl']" fontWeight="700">Contact me<span class="pink">!</span></c-text>
              <c-stack spacing="3">
                <c-text fontSize="sm" class="gray-500" fontWeight="400">Send me a message if you would like to talk</c-text>
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
    <c-box class="wow animate__fadeIn" pos="relative" align="center" :m="['-50px auto', '-50px auto', '-150px auto']">
        <c-box z-index="1">
          <lottie-player src="https://assets6.lottiefiles.com/temp/lf20_l0ORt3.json"  background="transparent"  speed="1"  style="width: 300px; height: 300px;"  loop autoplay>
          </lottie-player>
        </c-box>
        <c-box z-index="2" width="300px" pos="absolute" left="calc(50% - 140px)" bottom="20px">
          <c-text fontWeight="500" mt="-50px" color="#718096">The cats made me code this site</c-text>
          <c-text color="#718096" fontSize="14px">Copyright © 2021 Ha's cats & <a class="green" href="https://chakra-templates.dev/">Chakra</a></c-text>
        </c-box>
    </c-box>
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
        expanded: false,
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

