<script>
import axios from "axios";

export default {

  methods: {
    submitForm() {
      // Stucture the form data.
      let params = {
        company: this.companyName,
        email: this.formEmail,
        page: this.$route.fullPath
      }
      // Construct the form data into a query string.
      let query =
      Object.keys(params)
      .map(k => encodeURIComponent(k) + '=' + encodeURIComponent(params[k]))
      .join('&');
      let uri = "https://script.google.com/macros/s/AKfycbzdTk79pWTlNi5BMFn33FwGj2R6jMuxWoY40cNlinIrgv6Etz4/exec" + "?" + query;
      axios({
        method: "get",
        url: uri
      }).then(function(response) {});
      this.formStepFormShowToggle();
    },

    formStepFormShowToggle() {
      this.formStepFormShow = !this.formStepFormShow;
    },

    formStepSubmittedShowToggle() {
      this.formStepSubmittedShow = !this.formStepSubmittedShow;
    },

    submitFormTransitionLeave(el) {
      this.formStepSubmittedShowToggle();
    }
  },

  data() {
    return {
      formEmail: undefined,
      formStepFormShow: true,
      formStepSubmittedShow: false
    };
  },

  props: {
      companyName: {
          default: "unknown",
          type: String
      },

      infoText: {
          default: null,
          type: String
      },

      infoList: {
        default: null,
        type: Array
      }
  }
}

</script>

<template>
  <div class="contact-form py-5">
    <div class="row">
      <div class="col-12">
        <transition name="fade" v-on:after-leave="submitFormTransitionLeave">
          <div class="contact-form__form-step" v-if="formStepFormShow">
            <div class="contact-form__form-wrapper py-5 px-5">
                <div class="contact-form__info text-left">
                    <p v-if="infoText">{{ infoText }}</p>
                    <ul v-if="infoList">
                        <li v-for="item in infoList">{{ item }}</li>
                    </ul>
                </div>
                <form class="contact-form__step contact-form__step-form m-auto">
                  <div class="form-group text-left">
                    <label for="contact-form__email">Email Address</label>
                    <input id="contact-form__email" type="email" name="email" class="form-control" v-model="formEmail" placeholder="Email"/>
                  </div>
                  <div>
                    <button @click.prevent="submitForm" type="submit" class="btn btn-primary px-5 w-100" id="submit-form">Submit</button>
                  </div>
                </form>
            </div>
          </div>
        </transition>
        <div class="contact-form__step contact-form__step-submitted" v-if="formStepSubmittedShow">
          <h2>Thank you for reaching out. We will get back to you about your selected meetups.</h2>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
.contact-form__step {
  max-width: 600px;
  margin: 0 auto;
}

.contact-form__form-wrapper {
  margin: 15px;
  transition: 1s;
  border: 1px solid lightgrey;
  box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.2);
}

.contact-form__header {
  text-align: center;
}

.fade-enter-active, .fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>
