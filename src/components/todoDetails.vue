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