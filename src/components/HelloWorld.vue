<template>
<div class="hello">
  <div class="todoForm">
    <form class="form-inline mb-3" v-on:submit.prevent="addNewItem">
      <input id="inline-form-input-name" name="item" v-model="name" class="mb-2 mr-sm-2 mb-sm-0 form-control" placeholder="Please Enter Name" required/>
      <button class="form-control bg-info text-white">Add</button>
    </form>
    <ul class="list-unstyled">
      <li v-for="(item,i) in items" :key="`item-${i}`" class="text-left">
        <input type="checkbox" :id="i" :value="item"/>
        <label :for="i">{{ item }}</label>
      </li>
    </ul>
  </div>
</div>
</template>

<script>
export default {
  data () {
    return {
      name: null,
      items: []
    }
  },
  methods: {
    addNewItem () {
      // console.log(this.item)
      this.items.push(this.name)
    }
  }
}
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.todoForm {
  width: 400px;
  margin: 50px auto;
}
  ul input:checked + label{
    text-decoration: line-through;
    text-decoration-color: gray;
  }
</style>
