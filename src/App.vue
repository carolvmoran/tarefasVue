<template>
	<div id="app">
		<h1><i class="fas fa-list-ol"></i> Tarefas</h1>
		<NewTask @taskAdded="addTask" />
		<TaskGrid @taskDeleted="deleteTask" :tasks="tasks"/>
	</div>
</template>

<script>
import TaskGrid from './components/TaskGrid.vue'
import NewTask from './components/NewTask.vue'

export default {
	components: { TaskGrid, NewTask },
	data() {
		return {
			tasks: []
		}
	},
	methods: {
		addTask(task) {
			const sameName = t => t.name === task.name
			const reallyNew = this.tasks.filter(sameName).length == 0
			if(reallyNew) {
				this.tasks.push({
					name: task.name,
					pending: task.pending || true 
				})
			}
		},
		deleteTask(i){
			this.tasks.splice(i, 1)
		}
	},
}
</script>

<style>
	body {
		font-family: 'Lato', sans-serif;
		background: linear-gradient(to right, #fc354c, #0ce9e5);
		color: #FFF;
	}

	#app {
		display: flex;
		flex: 1;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		height: 100vh;
	}

	#app h1 {
		margin-bottom: 5px;
		font-weight: 300;
		font-size: 3rem;
		text-shadow: 2px 2px 2px black;
	}
</style>
