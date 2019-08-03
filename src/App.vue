<template>
  <div class="container">
    <div class="columns is-centered is-multiline">
      <EmployeeCard v-for="employee in Employees.Employees" :employee="employee" />
    </div>
  </div>
</template>

<script>
/**
 *
 */
import EmployeeCard from "./components/EmployeeCard.vue";
import Employees from "./../data/employees.json";

export default {
  name: "app",
  components: {
    EmployeeCard
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
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
