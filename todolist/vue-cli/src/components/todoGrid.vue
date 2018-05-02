<!-- grid containing all the yet made todo -->
<!-- todo must be card -->
<!-- and the data input should be in ordered list -->

<template>
	<div class="row">
		<app-todo v-for=" ( listItemObj , index ) in listItems" @click.native="deleteTodo(index)">
			<!-- loop through the listItems --> 
            <ul>
            	<li>
         			{{ listItemObj }}
            	</li>
            </ul>
		</app-todo>
	</div>
</template>

<script>
	import todo from './todo.vue';

	export default {
		props :['listItems'],

		methods:{
			deleteTodo(index){
				this.$emit('deleteTodoFromList', index)
			}
		},

		components :{
			appTodo : todo // registering the component locally
		}
	}
</script>

<style>
	
</style>