<template>
  <div>
    <carousel-3d :height="550">
      <Slide v-for="(person,i) in employees" :index="i" :employee="person">
        <div class>
          <div class="card-image">
            <figure class="image is-4by4">
              <img :src="'/img/' + person.image" />
            </figure>
            <div class="card-content has-text-centered">
              <div class="content">
                <h1 :class="[windowWidth>700 ? 'title is-3' : 'is-size-5']">{{person.name}}</h1>
                <h1 :class="[windowWidth>700 ? 'title is-5' : 'is-size-6']">{{person.role}}</h1>
                <a>{{person.twitter}}</a>
              </div>
            </div>
          </div>
        </div>
      </Slide>
    </carousel-3d>
  </div>
</template>
<script>
import { Carousel3d } from "vue-carousel-3d";
import Slide from "./Slide.vue";
import EmployeeCard from "./EmployeeCard.vue";

export default {
  name: "EmployeeCar",
  props: ["employees"],
  components: {
    Carousel3d,
    Slide,
    EmployeeCard
  },
  data: function() {
    return {
      msg: "Hello World! This is a Event listener test.",
      windowWidth: 0,
      windowHeight: 0
    };
  },

  mounted() {
    this.$nextTick(function() {
      window.addEventListener("resize", this.getWindowWidth);
      window.addEventListener("resize", this.getWindowHeight);

      //Init
      this.getWindowWidth();
      this.getWindowHeight();
    });
  },

  methods: {
    getWindowWidth(event) {
      this.windowWidth = document.documentElement.clientWidth;
    },

    getWindowHeight(event) {
      this.windowHeight = document.documentElement.clientHeight;
    }
  },
  beforeDestroy() {
    window.removeEventListener("resize", this.getWindowWidth);
    window.removeEventListener("resize", this.getWindowHeight);
  }
};
</script>
<style scoped>
</style>

