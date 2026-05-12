<template>
  <div>
    <h1>Todo App</h1>
    <v-card>
      <v-toolbar>
        <v-spacer></v-spacer>
        <v-btn color="primary" @click="dialog = true" variant="flat">Create</v-btn>
      </v-toolbar>
      <v-data-table :items="todos" :headers="headers">
        <template v-slot:item.actions="{item}">
          <v-btn @click="openEditDialog(item)">Edit</v-btn>
          <v-btn>Delete</v-btn>
        </template>
      </v-data-table>
    </v-card>

    <v-dialog v-model="dialog" width="500">
      <v-card>
          <v-toolbar>
            <v-toolbar-title>Create Todo</v-toolbar-title>
          </v-toolbar>

        <v-form class="ma-5">
          <v-text-field label="Title" v-model="title"</v-text-field>
          <v-text-field label="Priority" v-model="priority" type="number"></v-text-field>
          <v-date-input prepend-icon="" v-model="dueDate" label="Due Date"></v-date-input>
        </v-form>

        <v-card-actions>
          <v-btn @click="dialog = false">Cancel</v-btn>
          <v-btn @click="createTodo">Submit</v-btn>
        </v-card-actions>
        
      </v-card>

    </v-dialog>


    <v-dialog v-model="dialog" width="500">
      <v-card>
          <v-toolbar>
            <v-toolbar-title>Update Todo</v-toolbar-title>
          </v-toolbar>

        <v-form class="ma-5">
          <v-text-field label="Title" v-model="title"</v-text-field>
          <v-text-field label="Priority" v-model="priority" type="number"></v-text-field>
          <v-date-input prepend-icon="" v-model="dueDate" label="Due Date"></v-date-input>
        </v-form>

        <v-card-actions>
          <v-btn @click="dialog = false">Cancel</v-btn>
          <v-btn @click="UpdateTodo">Update</v-btn>
        </v-card-actions>
        
      </v-card>
    </v-dialog>



  </div>
</template>

<script setup>
const headers = [
  { title: 'ID', key: 'id'},
  { title: 'Title', key: 'title'},
  { title: 'Priority', key: 'priority'},
  { title: 'Due Date', key: 'dueDate'},
  { title: 'Status', key: 'completed'},
  { title: 'Actions', key: 'actions'}
]
const todos = ref([]);
const dialog = ref(true);
const updateDialog = ref(false);

const id = ref("");
const title = ref("");
const priority = ref(0);
const dueDate = ref(null);

const getTodos = async () => {
  const data = await $fetch('https://playground.mockoon.com/todos')

  todos.value = data;

  console.log(data);
};

const createTodo = async () => {
  try {

    const data = await $fetch("https://playground.mockoon.com/todos", {
      method: "POST",
      body: {
        title: title.value,
        priority: priority.value,
        dueDate: dueDate.value,
        completed: false
      }
    })

    console.log("Succesfully Created.", data);
    getTodos();

  } catch (err) {
    console.error("Failed to create.", err)
  }
}

// Function to load the data and open the update  dialog
const openEditDialog = async (item) => {
  console.log(item);
  title.value = item.title;
  priority.value = item.priority;
  dueDate.value = item.dueDate;
  id.value = item.id;

  updateDialog.value = true;
};

const updateTodo = async () => {
  try {

    const data = await $fetch(`https://playground.mockoon.com/todos/${id.value}`, {
      method: "PUT",
      body: {
        title: title.value,
        priority: priority.value,
        dueDate: dueDate.value,
        completed: false
      }
    })

    console.log("Succesfully Updated.", data);
    getTodos();

  } catch (err) {
    console.error("Failed to update.", err)
  }
}

onMounted(() => {
  getTodos();
})
</script>

