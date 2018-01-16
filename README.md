# Description
The vue side bar group tree


# Installation
npm i vue-sidebar-group-tree

# Using
vue-sidebar-group-tree  v-bind:items="categories" v-bind:item-id="categoryId" v-bind:sub-item-id="subcategoryId" v-bind:setting="setting"></vue-sidebar-group-tree>

this.$events.on('selectedItemFired', this.updateCategory);

this.$events.on('selectedSubItemFired', this.updateSubCategory);

categories = [
 {
          id: 1,
          name: 'Category 1',
          subitems: [
            {
              id: 1,
              name: 'SubCategory 1'
            }
          ]
        }
]

categoryId: null,

subcategoryId: null,

setting: {title: 'The title'}

# Sample
Refer to sample\ex
