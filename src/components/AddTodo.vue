<template>
  <div>
    <h3>Add Todo</h3>
    <div class="add">
      <form @submit.prevent="onSubmit">
        <input type="text" v-model="title" placeholder="Add Todo" />
        <input type="submit" value="Submit">
      </form>
    </div>
  </div>
</template>

<script>
import { mapActions } from 'vuex';

export default {
  name: "AddTodo",
  data() {
    return {
      title: ''
    }
  },
  methods: {
    ...mapActions(["addTodo"]),
    onSubmit() {
      if(this.title === ''){
        alert('Please enter title!')
      } else {
      this.addTodo(this.title);
      this.title = '';
      }
    }
  }
}
</script>

<style scoped>
  form {
    display: flex;
  }

  input[type="text"] {
    padding: 10px;
    border: 1px solid #41b883;
    outline: 0;
    width: 500px;
    margin-right: 0;
    margin-left:auto;
  }

  input[type="submit"] {
    background-color: #2596be;
    border: 1px solid #41b883;
    cursor: pointer;
     margin-right: auto;
    margin-left:0;
  }
</style>