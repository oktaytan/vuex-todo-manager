<template>
  <div>
    <h3 class="title">Add Todo</h3>
    <div class="add">
      <form @submit="onSubmit">
        <input type="text" v-model="title" placeholder="Add Todo...">
        <input type="submit" value="Submit">
      </form>
    </div>
  </div>
</template>

<script>
import { mapActions } from "vuex";

export default {
  name: "AddTodo",
  data() {
    return {
      title: ""
    };
  },
  methods: {
    ...mapActions(["addTodo"]),
    onSubmit(e) {
      e.preventDefault();
      this.addTodo(this.title);
    }
  }
};
</script>

<style scoped>
form {
  display: flex;
}
input[type="text"] {
  flex: 10;
  padding: 10px 15px;
  border: 1px solid #00d2d3;
  outline: 0;
  border-top-left-radius: 1.5rem;
  border-bottom-left-radius: 1.5rem;
  font-size: 1.1rem;
}
input[type="submit"] {
  flex: 2;
  background: #01a3a4;
  color: #fff;
  border: 1px #01a3a4 solid;
  cursor: pointer;
  border-top-right-radius: 1.5rem;
  border-bottom-right-radius: 1.5rem;
  font-size: 1.1rem;
}
</style>
