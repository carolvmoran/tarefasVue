<template>
    <div @click="$emit('taskStateChanged', task)" class="task" :class="stateClass">
        <span class="close" @click.stop="$emit('taskDeleted', task)"><i class="far fa-trash-alt"></i></span>
        <p>{{ task.name }}</p>
    </div>
</template>
<script>
export default {
    props: {
        task: { type: Object, required: true}
    },
    computed: {
        stateClass() {
            return {
                pending: this.task.pending,
                done: !this.task.pending 
            }
        }
    }
}
</script>
<style>
    .task {
        position: relative;
        box-sizing: border-box;
        border-radius: 8px;
        width: 350px;
        height: 150px;
        padding: 10px;
        font-size: 2rem;
        font-weight: 300;
        cursor: pointer;
        user-select: none;
        display: flex;
        justify-content: center;
        align-items: center;
    }   
    .pending {
        border-left: 15px solid #c93446;
        background-color: #fc354c;
        box-shadow: 2px 2px 2px black;
    }
    .done {
        border-left: 15px solid #25D5D4;
        background-color: #6EA0A7;
        text-decoration: line-through;
        box-shadow: 2px 2px 2px black;
    }
    .pending .close{
        background-color: #25D5D4;
    }
    .done .close{
        background-color: #c93446;
    }
    .close{
        position: absolute;
        right: 10px;
        top: 10px;
        font-size: 1rem;
        border-radius: 15px;
        padding: 5px;
        display: flex;
        justify-content: center;
        text-shadow: 2px 2px 2px black;
    }
</style>