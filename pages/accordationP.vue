<template>
  <div>
    <div class="faqs">
      <FAQ
        v-for="(faq, i)
        in faqs" 
        :key="i" 
        :faq="faq" 
        :index="i"
        :open="faq.open"
        @toggleOpen="toggleOpen(i)"
        />
    </div>
  </div>
</template>

<script>
export default {
    data() {
        return {
            faqs: [
                {
                    question: "who is the best super hero?",
                    answer: "i'm not sure but we love his 3000",
                    open: false
                },
                {
                    question: "what is Goka's called with thite hair?",
                    answer: "master ultra instrict?",
                    open: false
                },
                {
                    question: "have you liked & subscribed yet?",
                    answer: "yes",
                    open: false
                }
            ]
        };
    },
    methods:{
      toggleOpen: function (index) {
        this.faqs = this.faqs.map((faq, i) => {
        if (index === i) {
          faq.open = !faq.open;
        } else {
          faq.open = false;
        }
        return faq;
      });
    }
  }
}
</script>

<style>
  .faq {
    display: block;
    width: 100%;
    max-width: 768px;
    margin: 15px auto;
    padding: 15px;
    border-radius: 8px;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, .2);
    background-color: #fff;
  }
  .faq .question {
    position: relative;
    color: #3c3c3c;
    font-size: 20px;
    transition: all .4s linear;
  }
  .faq .question::after {
    content: '';
    position: absolute;
    top: 50%;
    right: 0px;
    transform: translateY(-50%) rotate(0deg);
    width: 30px;
    height: 30px;
    background-image: url('../assets/arrow-down-thin.svg');
    background-position: center;
    background-size: contain;
    background-repeat: no-repeat;
    transition: all .4s linear;
  }
  .faq .answer {
    color: #3c3c3c;
    font-size: 18px;
    opacity: 0;
    max-height: 0px;
    overflow: hidden;
    transition: all .4s ease-out;
  }
  .faq.open{
    background-color: red;
  }
  .faq.open .question {
    margin-bottom: 15px;
  }
  .faq.open .question::after {
    transform: translateY(-50%) rotate(90deg);
  }
  .faq.open .answer {
    opacity: 1;
    max-height: 1000px;
  }
</style>