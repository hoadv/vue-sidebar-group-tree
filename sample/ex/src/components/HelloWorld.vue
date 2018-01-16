<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div style="width: 40%">
    <vue-sidebar-group-tree  v-bind:items="categories" v-bind:item-id="categoryId" v-bind:sub-item-id="subcategoryId" v-bind:setting="setting"></vue-sidebar-group-tree>
    </div>
  </div>
</template>

<script>
import  sidebarGroupTree from 'vue-sidebar-group-tree'
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'The vue-sidebar-group-tree sample',
      categories: [],
      selectedCategoryIndex: null,
      categoryId: null,
      subcategoryId: null,
      setting: {title: 'The title'}
    }
  },
  created() {
    this.categories = this.fetchCategories();
    this.$events.on('selectedItemFired', this.updateCategory);
    this.$events.on('selectedSubItemFired', this.updateSubCategory);
  },
  components: {
    'vue-sidebar-group-tree': sidebarGroupTree
  },
  methods: {
    updateCategory(index) {
      alert(index);
    },
    updateSubCategory(id) {
       alert(id);
    },
    fetchCategories() {
     return [
        {
          id: 1,
          name: 'Category 1',
          subitems: [
            {
              id: 1,
              name: 'SubCategory 1'
            }
          ]
        },
        {
          id: 2,
          name: 'Category 2',
          subitems: [
            {
              id: 2,
              name: 'SubCategory 2'
            },
            {
              id: 3,
              name: 'SubCategory 3'
            }
          ]
        }
     ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
