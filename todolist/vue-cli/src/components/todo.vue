<!-- child component responsible fr passing of all the data -->

<template>
	<div>
		<!-- wrapping div -->
		<div class="col listTodo">
				<slot>
						<!-- to send data -->
			    </slot>
		</div>
	</div>
</template>


<script>
	export default {
		props : ['listItems']
	}
</script>


<style scoped>
 textarea{
 	margin:auto;
 }
	.listTodo{
		cursor: pointer;
		font-size: 25px;
		font-size: bold;
		color:blue;
		border: 2px solid blue;
		margin: 5px;
		
	}
	.listTodo:hover{
		background-color: #FAA09C;
	}
</style>