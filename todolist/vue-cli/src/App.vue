<template>
  <div>
    <!-- wrapping div -->
    <div class="container">
      <app-new-todo @addTodo="TodoAddNew"></app-new-todo>
      <hr>
      <app-todo-grid :listItems="listItems" @deleteTodoFromList="deleting">
        <!--
        * to bind the grid two way with the listItems and hence :listItems, which I want to be     passed in from todoGrid.vue 
        * :listItems -> this is here in data
        * ="listItems" -> this  is the prop to be passed in  ie the array in here
        -->
      </app-todo-grid>
    </div>

  </div>
</template>

<script>
  import todoGrid from "./components/todoGrid.vue";
  import newTodo from "./components/newTodo.vue";
  
  export default {
    data(){
        return{
          listItems: ['sample-gets deleted when user inputs'],
          maxListItem : 10
        }
    },
    methods:{
      TodoAddNew(NewTodoInList, counter){
        if(counter==0){
        this.listItems.splice(0 , 1);
        }
        this.listItems.push(NewTodoInList);       
      },
      deleting(index){
        this.listItems.splice(index , 1);
      }
    },
    components:{
     // todoGrid's is being worked on at first hence its component is to be regitstered first
     appTodoGrid:todoGrid,
     appNewTodo: newTodo
    }
  }
</script>

<style></style>