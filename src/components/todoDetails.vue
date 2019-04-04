<template>
  <div>
<li
  class="text-left"
>
  <input
    type="checkbox"
    :value="name"
    :checked="checked"
    :id="id"
    @change="changeCheckbox"
  />
  <label :for="id"
  >{{ name }}</label>
</li>
</div>
</template>
<script>
export default {
  props: ['name', 'checked', 'id'],
  methods: {
    changeCheckbox () {
      this.$emit('checkchange')
    }
  }
}
</script>
