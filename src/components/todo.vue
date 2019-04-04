<template>
<div class="todo">
  <div class="todoForm">
    <form class="form-inline mb-3" v-on:submit.prevent="addNewItem">
      <input id="inline-form-input-name" name="item" v-model="name" class="mb-2 mr-sm-2 mb-sm-0 form-control" placeholder="Jane Doe" required/>
      <button class="form-control bg-info text-white">Add</button>
    </form>
    <div class="d-flex align-self-center justify-content-between">
      <div
      class="pending"
      v-if="items.length>0"
      >
        <div
        v-show="itemsTodo.length"
        >({{ itemsTodo.length }} Pending)</div>
        <!-- <h5>Pending</h5> -->
        <ul class="list-unstyled">
          <li
            v-for="(item,i) in itemsTodo"
            :key="`item-${i}`"
            class="text-left"
          >
            <input
              type="checkbox"
              :id="i"
              :value="item.name"
              :checked="item.checked"
              @change="item.checked = !item.checked"
            />
            <label
              :for="i"
            >{{ item.name }}</label>
          </li>
        </ul>
      </div>
      <div class="done" v-if="itemsDone.length>0">
        <div
        v-show="itemsDone.length"
        >({{ itemsDone.length }} Done)</div>
        <!-- <h5>Done</h5> -->
        <ul class="list-unstyled">
            <li
            v-for="(item,i) in itemsDone"
            :key="`item-${i}`"
            class="text-left">
              <label :for="i">{{ item.name }}</label>
            </li>
        </ul>
      </div>
    </div>
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
  computed: {
    itemsDone () {
      return this.items.filter(item => item.checked)
    },
    itemsTodo () {
      return this.items.filter(item => !item.checked)
    }
  },
  methods: {
    addNewItem () {
      // console.log(this.item)
      const newEntry = {
        name: this.name,
        checked: false
      }
      this.items.push(newEntry)
      this.name = null
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
</style>
