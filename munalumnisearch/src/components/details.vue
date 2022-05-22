<template>
  <div class="detail" v-if="isDetailsOpen">
    <div class="detail-container">
      <dl>
        <dt>Name</dt>
        <dd>John Doe</dd>
        <dt>E-mail</dt>
        <dd>email@example.com</dd>
        <dt>City</dt>
        <dd>Princeton, NJ</dd>
        <dt>Phone-Number</dt>
        <dd>555-555-5555</dd>
        <dt>Last Update</dt>
        <dd>May 15 2020</dd>
        <dt>Notes</dt>
        <dd>
          Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Donec odio.
          Quisque volutpat mattis eros. Nullam malesuada erat ut turpis.
          Suspendisse urna nibh, viverra non, semper suscipit, posuere a, pede.
        </dd>
      </dl>
    </div>
    <div class="detail-nav">
      <button class="close" @click="toggleDetails">Close</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Details",
  props: ["isDetailsOpen"],
  methods: {
    toggleDetails() {
      this.$parent.toggleDetails();
    },
  },
};
</script>

<style>
.button {
  line-height: 1;
  display: inline-block;
  font-size: 1.2rem;
  text-decoration: none;
  border-radius: 5px;
  color: #fff;
  padding: 8px;
  background-color: #4b908f;
}

.select {
  padding-bottom: 20px;
  border-bottom: 1px solid #28333f;
}
.select:before {
  display: none;
}

.detail {
  background-color: #405052;
  width: 100%;
  height: 100%;
  padding: 40px 0;
  position: fixed;
  display: block;
  top: 0;
  left: 0;
  border: 5px solid #464655;
  position: fixed;

  /* overflow: auto;
  -moz-transform: translateX(-100%);
  -ms-transform: translateX(-100%);
  -webkit-transform: translateX(-100%);
  transform: translateX(-100%);
  -moz-transition: -moz-transform 0.3s ease-out;
  -o-transition: -o-transform 0.3s ease-out;
  -webkit-transition: -webkit-transform 0.3s ease-out;
  transition: transform 0.3s ease-out; */
}
/* .detail.open {
  -moz-transform: translateX(0);
  -ms-transform: translateX(0);
  -webkit-transform: translateX(0);
  transform: translateX(0);
} */

.detail-container {
  margin: 0 auto;
  padding: 40px;
  max-width: 500px;
}

dl {
  margin: 0;
  padding: 0;
}

dt {
  font-size: 2.2rem;
  font-weight: 300;
}

dd {
  margin: 0 0 40px 0;
  font-size: 1.8rem;
  padding-bottom: 5px;
  border-bottom: 1px solid #464655;
  box-shadow: 0 1px 0 #464655;
}

.close {
  background: none;
  padding: 18px;
  color: #fff;
  font-weight: 300;
  border: 1px solid rgba(255, 255, 255, 0.4);
  border-radius: 4px;
  line-height: 1;
  font-size: 1.8rem;
  position: fixed;
  right: 40px;
  top: 20px;
  -moz-transition: border 0.3s linear;
  -o-transition: border 0.3s linear;
  -webkit-transition: border 0.3s linear;
  transition: border 0.3s linear;
}
.close:hover,
.close:focus {
  background-color: #94958b;
  border: 1px solid #464655;
}
</style>
