<template>
  <div class="home">
    <!-- NAVIGATION -->
    <div class="navBar center">
      <el-button type="primary" v-on:click="buttonClick()">CLICK ME</el-button>
    </div>
    {{ result }}
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Home",
  components: {},
  data() {
    return {
      result: "",
    };
  },
  methods: {
    buttonClick() {
      axios.get("https://jsonplaceholder.typicode.com/todos/").then((res) => {
        console.log(res);
        this.result = res;
      });
    },
  },
};
</script>

<style scoped>
.center {
  display: flex;
  justify-content: center;
  margin: 1rem;
}
</style>