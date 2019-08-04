<template>
  <div class="tinted-image">
    <div class="back"></div>
    <div class="container">
      <div class="columns">
        <div class="column is-two-fifths"></div>
        <div class="column is-two-fifths">
          <h1 class="title is-1">..so call me maybe</h1>
        </div>
      </div>
      <div class="columns">
        <div class="column is-two-fifths"></div>
        <div v-if="!form.submitted" class="column is-two-fifths">
          <div class="field">
            <label class="label">Name</label>
            <div class="control has-icons-left has-icons-right">
              <input
                v-model="form.name"
                :class="[nameIsValid ? 'input success' : 'input']"
                type="text"
                placeholder="Text input"
              />
              <span class="icon is-small is-left">
                <i class="fas fa-user"></i>
              </span>
              <span v-if="nameIsValid" class="icon is-small is-right">
                <i class="fas fa-check"></i>
              </span>
              <p v-if="!nameIsValid" class="help">This field is required</p>
            </div>
          </div>
          <div class="field">
            <label class="label">Email</label>
            <div class="control has-icons-left has-icons-right">
              <input
                v-model="form.email"
                :class="[emailIsValid ? 'input success' : 'input']"
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
              <p v-if="!emailIsValid" class="help">This field is required</p>
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
              <button :disabled="!formIsValid" @click="submitForm" class="button is-primary">Send</button>
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
  </div>
</template>
<script>
/**
 * validateEmail function should be a nodejs module that can be reused,
 * for this excercise I put it within the component
 * The form checks if the two mandatory fields (name and email)
 * In the case of email it checks if email is correct
 */

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

        // if true, form is gone and user gets feedback of submission
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
.title {
  padding-top: 1em;
  color: #cad0e3;
}
input,
textarea {
  color: #cad0e3;
  background-color: #263761;
}
.select select,
.textarea,
.input {
  border-color: transparent;
}

.container {
  padding: 1em;
}

.label {
  color: #cad0e3;
}

/*Component background*/
.invert {
  background-color: #05102b;
}

.input::placeholder {
  color: #818ba3;
  opacity: 1; /* Firefox */
}
/*Valid input */
.success {
  color: white;
  background-color: #fd7208;
}

.control.has-icons-left .input:focus ~ .icon,
.control.has-icons-left .select:focus ~ .icon,
.control.has-icons-right .input:focus ~ .icon,
.control.has-icons .select:focus ~ .icon {
  color: white;
}

.tinted-image {
  background: 
    /* top, transparent red, faked with gradient */ linear-gradient(
      rgba(38, 55, 97, 0.45),
      rgba(38, 55, 97)
    ),
    /* bottom, image */ url(../assets/alion-back.jpg);
  background-repeat: no-repeat;
  height: 110vh;
}

.back {
  z-index: -1;
  /* margin-bottom: 1.8rem; */
  width: 100%;
  height: 110vh;
  background-color: black;
  position: absolute;
}
</style>
