<template>
  <div id="app">
    <link
      rel="stylesheet"
      href="https://use.fontawesome.com/releases/v5.2.0/css/all.css"
      integrity="sha384-hWVjflwFxL6sNzntih27bfxkr27PmbbK/iSvJ+a4+0owXq79v+lsFkW54bOGbiDQ"
      crossorigin="anonymous"
    />
    <Nav></Nav>
    <div class="section">
      <EmployeeCar :employees="Employees.Employees" />
    </div>

    <!-- <div class="container section">
      <div class="columns is-centered is-multiline is-variable is-7">
        <EmployeeCard v-for="employee in Employees.Employees" :employee="employee" />
      </div>
    </div>-->
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
import EmployeeCar from "./components/EmployeeCar.vue";
import Nav from "./components/Nav.vue";

export default {
  name: "app",
  components: {
    EmployeeCard,
    ContactForm,
    EmployeeCar,
    Nav
  },
  data() {
    return {
      Employees
    };
  }
};
</script>

<style lan="scss">
.container.section {
  width: 70%;
}
</style>
