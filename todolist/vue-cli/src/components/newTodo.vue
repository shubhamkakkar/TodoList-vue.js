<!-- new todo's to  be added from here -->
<template>
	<div class="row">
		<div class="col">
			<form>
			<div class="form-group">
			 <h4 class="text-center">Todo List</h4>
			 <textarea rows="5" class="btn-block" v-model="NewTodoInList"></textarea>
		    </div>
		</form>
		</div>
		<div>
			<button class="btn btn-primary btn-block" @click.prevent="createTodo " @click="counter++">Add todo</button>
		</div>

	</div>
</template>

<script>
	export default{
		data(){
			return{
              NewTodoInList : [''],
              counter:0
			};
		},
		methods : {
			createTodo(){
				this.$emit("addTodo", this.NewTodoInList, this.counter);
				this.NewTodoInList = '';
			}/*,
			counterInc(){
				counter++;
			}*/
		}
	}

</script>

<style>
	.col{
 	margin:auto;
 }
</style>