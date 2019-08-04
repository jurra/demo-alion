<template>
  <div class="container">
    <h1 class="title is-1 has-text-centered">..so call me maybe</h1>
    <div class="columns">
      <div class="column is-one-third"></div>
      <div class="column is-two-fifths">
        <div class="field">
          <label class="label">Name</label>
          <div class="control">
            <input v-model="form.name" class="input" type="text" placeholder="Text input" />
          </div>
        </div>
        <div class="field">
          <label class="label">Email</label>
          <div class="control has-icons-left has-icons-right">
            <input
              v-model="form.email"
              class="input is-danger"
              type="email"
              placeholder="Email input"
              value="hello@"
            />
            <span class="icon is-small is-left">
              <i class="fas fa-envelope"></i>
            </span>
            <span class="icon is-small is-right">
              <i class="fas fa-exclamation-triangle"></i>
            </span>
          </div>
          <p class="help is-danger">This email is invalid</p>
        </div>

        <div class="field">
          <label class="label">Message</label>
          <div class="control">
            <textarea class="textarea" placeholder="Textarea"></textarea>
          </div>
        </div>

        <div class="field is-grouped">
          <div class="control">
            <button @click="submitForm" class="button is-link">Submit</button>
          </div>
          <div class="control">
            <button class="button is-text">Cancel</button>
          </div>
        </div>
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
        email: null
      }
    };
  },
  computed: {
    emailIsNotValid() {
      console.log("email not valid");
    }
  },
  methods: {
    submitForm() {
      const emailIsValid = validateEmail(this.form.email);
      const nameIsValid = !!this.form.name;
      const formIsValid = nameIsValid && emailIsValid;

      if (formIsValid) {
        console.log("Form Submitted", this.form);
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
