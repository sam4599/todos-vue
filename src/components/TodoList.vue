<template>
  <div>
    <todo-item
    v-for="todo of todos"
    v-bind:todo="todo"
    v-on:remove-todo="removeTodo"
    />

  </div>
</template>

<script>
import TodoItem from "@/components/TodoItem.vue";
export default {
    name: 'TodoList',
    props: ['todos'],
    components: {
        TodoItem
    },
    methods: {
        removeTodo(id) {
            this.$emit('remove-todo', id)
        }
    }
}
</script>