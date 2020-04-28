<template>
    <div class="item" v-bind:class="{'isdone':todoitem.completed}">
        <p>
            <input type="checkbox" v-on:change="markchange">
            {{todoitem.title}}
            <button @click="$emit('del-item',todoitem.id)" class="del">X</button>
        </p>
        
        
    </div>
</template>

<script>
export default {
    nam: 'Todoitem',
    props:["todoitem"],

    methods:{
        markchange(){
            this.todoitem.completed =!this.todoitem.completed;
        }
    }
}
</script>

<style scoped>
    .item{
        background-color:gray;
        padding:10px;
        margin:20px;
        display:flex;
        justify-content:space-evenly;
        align-items: center;
        }
    .isdone{
        text-decoration: line-through;
    }
    .del{
        border-radius: 90px;
        background-color: red;
    }

</style>



