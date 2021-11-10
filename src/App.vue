<template>
  <router-view />
</template>

<script>
import axios from "axios";

export default {
  data: function() {
    return { users: [] };
  },
  methods: {
    load() {
      axios
        .get("https://ghibliapi.herokuapp.com/films")
        .then((res) => {
          this.users = res.data; //respon dari rest api dimasukan ke users
          console.log(res.data);
        })
        .catch((err) => {
          console.log(err);
        });
    },
  },
  mounted() {
    this.load()
  },
};
</script>
