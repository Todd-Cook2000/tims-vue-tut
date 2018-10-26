<template>
  <v-layout align-center justify-start column>
    <!-- Todo Form -->
    <v-form>
        <v-text-field
        label="Add Todo Item "
        v-model= "todoitem"
        ></v-text-field>
    </v-form>
    <!-- Add Item Button -->
    <v-btn>Add Item @click="() => </v-btn>
    <!-- Todo List -->
    <v-list one-line>
      <template v-for="(item, index) in todoListItem">
        <v-list-tile
            :key= "index"
        >
          <v-list-tile-content>
            <v-list-tile-title>{{ item }}</v-list-tile-title>
          </v-list-tile-content>
          <v-list-tile-action>
            <v-btn icon ripple @click="() => deleteItem(index)">
              <v-icon>delete</v-icon>
            </v-btn>
          </v-list-tile-action>
        </v-list-tile>
      </template>
    </v-list>
  </v-layout>
</template>

<script>
export default{
  data() {
    return {
      todoItem: null,
      todoListItem: [
        'Make Tutorial',
        'Milk Cat',
        'Get Tacos',
        'Eat Tacos',
      ],
    };
  },
  methods:{
    deleteItem(atIndex) {
      this.todoListItem.splice(atIndex, 1)
    },
    addItem(){
      this.todoListItem = [this.todoItem, ...this.todoListItem];
    }
  }
};
</script>

<style>

</style>

