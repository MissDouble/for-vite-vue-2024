<script setup>
import { ref } from 'vue'

const text = ref("這是一段文字")

const addTodo = ()=>{
    todos.value.push({
        text:text.value,
        id:new Date().getTime()
    });
    console.log(todos.value);
    text.value ='';
}

const deleteTodo = (todo) => {
    console.log(todo);
    const index = todos.value.findIndex(item => item.id === todo.id)
    console.log(index);
    todos.value.splice(index, 1);
}

const tempEdit = ref({
    id:'',
    text:''
})

const prepareEdit = (todo) => {
    tempEdit.value = {...todo};//拷貝
    console.log(tempEdit.value)
}

const confirmEdit = () => {
    const index = todos.value.findIndex(item => item.id === tempEdit.value.id)
    console.log(index);
    todos.value[index] = tempEdit.value;
    tempEdit.value ='';
}

const todos = ref([
    {
        id:123,
        text:'12345',

    }
])
</script>

<template>
    <input type="text" v-model="text">
    <button @click='addTodo' type="button">新增</button>
    <hr>
    <div v-for="todo in todos" :key="todo.id">
        {{ todo.text }} 
        <button type="button" @click="deleteTodo(todo)">刪除</button>
        <button type="button" @click="prepareEdit(todo)">編輯</button>
    </div>
    <hr>
    <div v-if="tempEdit.id">
        <h2>編輯區域</h2>
        當前修改的值:{{ tempEdit.text }} <br>
        <input type="text" v-model="tempEdit.text">
        <button type="button" @click="confirmEdit">確認編輯</button>
        <button type="button" @click="tempEdit={}">取消</button>
    </div>
</template>