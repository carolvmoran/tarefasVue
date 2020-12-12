<template>
    <div class="new-task">
        <input v-model="name" @keydown.enter="add" type="text" class="form-element" placeholder=" Nova Tarefa? ">
        <button @click="add" class="form-element"><i class="fas fa-user-edit"></i></button>
    </div>
</template>
<script>
export default {
    data() {
        return {
            name: ''
        }
    },
    methods: {
        add() {
            this.$emit('taskAdded', { name: this.name })
            this.name = ''
        }
    },
}
</script>
<style>
    .new-task {
        margin: 35px;
    }
    .form-element {
        outline: none;
        font-size: 2rem;
        border: 1px solid #ffffff;
        padding: 10px 10px 10px 15px;
        color: #ffffff;
        box-shadow: 2px 2px 2px black;
    }
    input.form-element {
        width: 500px;
        background: #FFF2;
        border-top-left-radius: 8px;
        border-bottom-left-radius: 8px;
    }
    .form-element::-webkit-input-placeholder {
        color: #fff8;
        font-size: 1.5rem;

    }
    button.form-element {
        border-left: none;
        background-color: #fc354c;
        border-top-right-radius: 8px;
        border-bottom-right-radius: 8px;
        cursor: pointer;
        text-shadow: 2px 2px 2px black;
    }
</style>