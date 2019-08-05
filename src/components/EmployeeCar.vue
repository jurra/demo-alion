<template>
  <div>
    <carousel-3d :height="520">
      <Slide v-for="(person,i) in employees" :index="i" :employee="person">
        <div class>
          <div class="card-image">
            <figure class="image is-4by4">
              <img :src="'/img/' + person.image" />
            </figure>
            <div class="card-content has-text-centered">
              <h1 class="title is-3">{{person.name}}</h1>
              <div class="content">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Phasellus nec iaculis mauris.
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
  }
};
</script>
