<template>
   <div id="rootel">
    <div class="taskholder" v-bind:key="tasks.id" v-for="tasks in todos1">
        <TodoItem v-bind:todoitem="tasks" v-on:del-item="$emit('del-item',tasks.id)"></TodoItem>
    </div>
   </div>
</template>

<script>
import TodoItem from './TodoItems'

export default {
    name: "Todos",
    props:["todos1"],

    components:{
        TodoItem
    }
}
</script>
<style scoped>
    #rootel{
        border:2px solid red;
    }
    .taskholder{
        border:2px solid blue;
        margin:5px;
    }

</style>

