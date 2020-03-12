<template>
    <div>
        <form @submit="addToDo">
            <input type="text" name="title" v-model="title" placeholder="Add To Do">
            <input type="submit" value="Submit" class="btn">
        </form>
    </div>
</template>

<script>
//   import UUID from 'uuid';
    export default {
        name: 'AddToDo',
        data() {
            return {
                title: ''
            }
        },
        methods: {
            addToDo(e) {
                e.preventDefault();
//                console.log("newToDo",UUID);
                const newToDo = {
//                    id: UUID,
                    title: this.title,
                    completed: false
                }
//                send to parents
                this.$emit('add-todo', newToDo);
                this.title = '';
            }
        }
    }
</script>

<style scoped>
    form {
        display: flex;
    }

    input[type="text"] {
        flex: 10;
        padding: 5px;
    }

    input[type="submit"] {
        flex: 2;
    }
</style>