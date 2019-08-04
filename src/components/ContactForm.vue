<template>
  <div class="container">
    <h1 class="title is-1 has-text-centered">..so call me maybe</h1>
    <div class="columns">
      <div class="column is-one-third"></div>
      <div v-if="!form.submitted" class="column is-two-fifths">
        <div class="field">
          <label class="label">Name</label>
          <div class="control has-icons-left has-icons-right">
            <input
              v-model="form.name"
              :class="[nameIsValid ? 'input is-success' : 'input']"
              type="text"
              placeholder="Text input"
            />
            <span class="icon is-small is-left">
              <i class="fas fa-user"></i>
            </span>
            <span v-if="nameIsValid" class="icon is-small is-right">
              <i class="fas fa-check"></i>
            </span>
            <p v-if="!nameIsValid" class="help is-danger">This field is required</p>
          </div>
        </div>
        <div class="field">
          <label class="label">Email</label>
          <div class="control has-icons-left has-icons-right">
            <input
              v-model="form.email"
              :class="[emailIsValid ? 'input is-success' : 'input']"
              type="email"
              placeholder="Email input"
              value="hello@"
            />
            <span class="icon is-small is-left">
              <i class="fas fa-envelope"></i>
            </span>
            <span v-if="emailIsValid" class="icon is-small is-right">
              <i class="fas fa-check"></i>
            </span>
            <p v-if="!emailIsValid" class="help is-danger">This field is required</p>
          </div>
        </div>

        <div class="field">
          <label class="label">Message</label>
          <div class="control">
            <textarea v-model="form.message" class="textarea" placeholder="Textarea"></textarea>
          </div>
        </div>

        <div class="field is-grouped">
          <div class="control">
            <button :disabled="!formIsValid" @click="submitForm" class="button is-link">Send</button>
          </div>
          <div class="control">
            <button class="button is-text">Cancel</button>
          </div>
        </div>
      </div>
      <div v-if="form.submitted" class="column is-two-thirds">
        <h3 class="title is-3">
          Thank you very much {{form.name}} :)
          <br />We will contact you soon!
        </h3>
      </div>
    </div>
  </div>
</template>
<script>
// Email validation function (should be a  node module to be reused in different components)
function validateEmail(email) {
  var re = /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
  return re.test(String(email).toLowerCase());
}
export default {
  data() {
    return {
      form: {
        name: null,
        email: null,
        message: null,
        submitted: false
      }
    };
  },
  computed: {
    nameIsValid() {
      return !!this.form.name;
    },
    emailIsValid() {
      return validateEmail(this.form.email);
    },
    formIsValid() {
      return this.nameIsValid && this.emailIsValid;
    }
  },
  methods: {
    submitForm() {
      if (this.formIsValid) {
        this.$set(this.form, "submitted", true);
      } else {
        console.log("X Invalid form");
      }
    }
  }
};
</script>
<style scoped>
.form {
  background-color: #05102b;
}

.formContainer {
  width: 500px;
}
</style>
