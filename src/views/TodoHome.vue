<template>
    <div>
        <the-header />
        <div class="global-container">
            <h1>Список задач</h1>
            <div class="todo-create-click">
                <h2>Список задач пуст</h2>
                <button class="button-create">+ СОЗДАТЬ</button>
            </div>
            <todo-list
                v-bind:todos="todos"
                @remove-todo="removeTodo"
            />
        </div>
    </div>

</template>

<script>
import TheHeader from "@/components/TheHeader.vue";
import TodoList from "@/components/TodoList.vue";
import AppButton from "@/components/ui/AppButton.vue";
    export default {
    name: 'TodoCreate',
    components: {
        AppButton,
        TheHeader, TodoList
    },
        data() {
        return {
            todos: [
                {id: 1, title: 'Купить хлеб', completed: false},
                {id: 2, title: 'Купить чай', completed: false},
                {id: 3, title: 'Купить сахар', completed: false}
            ]
        }
    },
        methods: {
            removeTodo(id) {
                this.todos = this.todos.filter(t => t.id !== id)
            }
        }
}
</script>

<style scoped>
.global-container h1 {
    font-weight: 700;
    font-size: 24px;
    line-height: 33px;
    margin-top: 52px;
}

h2 {
    margin-top: 40px;
}

.button-create {
    padding: 10px 20px;
    margin-top: 30px;
    border-color: cadetblue;
    background: transparent;
    color: cadetblue;
}

.todo-create-click {
    display: flex;
    align-items: center;
    flex-direction: column;
}
</style>