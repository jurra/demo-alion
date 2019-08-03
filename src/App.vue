<template>
  <div id="app" class="container">
    <EmployeCard msg="New alion app" />
  </div>
</template>

<script>
/**
 * import json
 * for statement to load components
 */
import EmployeCard from "./components/EmployeeCard.vue";
import Employees from "./../data/employees.json";

export default {
  name: "app",
  components: {
    EmployeCard
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
