<template>
  <div>
    <h1>hello world</h1>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  data: function () {
    return {
      cars: []
    }
  },
  methods: {
    getCar: function () {
      axios.get('api/cars')
        .then((element) => {
          this.cars = element.data.results.data;

          console.log(this.cars);
        })
        .catch((error) => {
          console.log(error);
        })
    },
  },
  created() {
    this.getCar();
  },
};
</script>

<style>

</style>