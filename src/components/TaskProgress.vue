<template>
    <div class="task-progress">
        <span class="progress-value">{{ progress }}% Concluído</span>
        <div class="progress-bar" :style="{width: progress + '%'}"></div>
    </div>
</template>
<script>
export default {
    props: {
        progress: { type: Number, default: 0}
    }
}
</script>
<style>
    .task-progress{
        position: relative;
        width: 80%;
        border: 1px solid white;
        box-shadow: 2px 2px 2px black;
        color: white;
        border-radius: 8px;
        margin-bottom: 15px;
        margin-top: 30px;
        display: flex;
        flex-direction: column;
        align-items: center;
        
    }
    .progress-bar {
        position: absolute;
        border-radius: 8px;
        height: 100%;
        background-color: #fc354c;
        align-self: flex-start;
    }
    .progress-value {
        z-index: 1;
        font-size: 1.5rem;
    }
</style>