<template>
  <div id="app">
    <link
      rel="stylesheet"
      href="https://use.fontawesome.com/releases/v5.2.0/css/all.css"
      integrity="sha384-hWVjflwFxL6sNzntih27bfxkr27PmbbK/iSvJ+a4+0owXq79v+lsFkW54bOGbiDQ"
      crossorigin="anonymous"
    />
    <div class="container section">
      <div class="columns is-centered is-multiline is-variable is-7">
        <EmployeeCard v-for="employee in Employees.Employees" :employee="employee" />
      </div>
    </div>
    <ContactForm />
  </div>
</template>

<script>
/**
 *
 */

import Employees from "./../data/employees.json";
import EmployeeCard from "./components/EmployeeCard.vue";
import ContactForm from "./components/ContactForm.vue";

export default {
  name: "app",
  components: {
    EmployeeCard,
    ContactForm
  },
  data() {
    return {
      Employees
    };
  }
};
</script>

<style lan="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}

.container.section {
  width: 70%;
}
</style>
