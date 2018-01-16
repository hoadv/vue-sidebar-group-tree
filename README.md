# vue-sidebar-group-tree
The vue side bar group tree

# Installation
npm i vue-sidebar-group-tree

# Using
vue-sidebar-group-tree  v-bind:items="categories" v-bind:item-id="categoryId" v-bind:sub-item-id="subcategoryId" v-bind:setting="setting"></vue-sidebar-group-tree>

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
    },
    updateSubCategory(id) {
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
