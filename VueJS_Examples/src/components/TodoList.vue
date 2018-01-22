<template>
  <div>
    <h1>Todo List</h1>
    
    <div class="alert alert-primary" role="alert">
      This is a primary alert—check it out!
    </div>

    <div>
      <label>Add Item:
        <input v-model="newItemName" placeholder="Item Name">
      </label>
      <button v-on:click="addItem();"><i class="fa fa-check"/>Add</button>
    </div>

    <h2>Your Items</h2>
    <div v-for="item in todoListItems" v-bind:key="item">
      <p>Item Name: {{item.itemName}} ({{item.itemDescription}})</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoList",
  data() {
    return {
      newItemName: "",
      todoListItems: [
        {
          newItemName: "Test Item 1",
          itemDescription: "This is a test item"
        },
        {
          itemName: "Test Item 2",
          itemDescription: "This is a test item"
        }
      ]
    };
  },
  methods: {
    addItem: function() {
      var self = this;

      var newItem = {
        itemName: self.newItemName,
        itemDescription: "A Manually Added Item"
      };

      self.todoListItems.push(newItem);

      self.newItemName = "";
    }
  }
};
</script>
