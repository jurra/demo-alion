<template>
  <div class="column is-one-third">
    <div class="card">
      <div class="card-image">
        <figure class="image is-4by4">
          <img
            v-if="!employee.image"
            src="https://bulma.io/images/placeholders/1280x960.png"
            alt="Placeholder image"
          />
          <img v-if="employee.image" :src="'/img/' + employee.image" />
        </figure>
      </div>
      <div class="card-content">
        <div class="media">
          <div class="media-left">
            <figure class="image is-48x48">
              <img src="https://bulma.io/images/placeholders/96x96.png" alt="Placeholder image" />
            </figure>
          </div>
          <div class="media-content">
            <p class="title is-4">{{employee.name}}</p>
            <p class="subtitle is-6">@johnsmith</p>
          </div>
        </div>

        <div class="content">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit.
          Phasellus nec iaculis mauris.
          <a>@bulmaio</a>.
          <a href="#">#css</a>
          <a href="#">#responsive</a>
          <br />
          <div class="button is-primary">Read more about {{employee.name}}</div>
          <br />
          <time datetime="2016-1-1">11:09 PM - 1 Jan 2016</time>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "EmployeeCard",
  props: ["employee"]
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.card {
  transition: transform 500ms;
}
.card:hover {
  /* transition */
  transition: transform 400ms;
  /* transform */
  transform: scale(1.05);
}
</style>
