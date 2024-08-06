<script setup>
import { ref } from 'vue';
const text = ref('卡斯柏')
const num = ref(1);
const imgSrc = ref('https://plus.unsplash.com/premium_photo-1722377372975-0e44ef181553?q=80&w=887&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D');
const add = () => {
    num.value++
}
const todos = ref([//定義vue的資料使用
  {
    id:0,
    name:'購買雜貨',
    dueDate:'2024-07-30',
    complete:true
}])


</script>

<template>
<h1>{{ text }}</h1>
<input type="text" v-model="text">

<h2>{{ num }}</h2>
<form action="">
    <!-- 若button裡面沒有加上 type="button" 在form裡面的button type是預設為submit，所以按了會reload歸回1-->
    <button  v-on:click="add">點我 1</button>
</form>
<!-- v-on縮寫@ -->
<button type="button" @click="add">點我 2</button>

<!-- <img src="{{ imgSrc }}" alt=""> 不能直接在屬性裡面加大括號 要使用v-bind -->
<img v-bind:src="imgSrc" alt="">
<!-- v-binf縮寫: -->
<img :src="imgSrc" alt="">

<div>
    <div v-for="todo in todos" v-bind:key="todo.id">
        {{  todo.name }} <br>
        {{ todo.dueDate }} <br>
        {{  todo.complete ? '是':'否' }} 
        <input type="checkbox" v-model="todo.complete">
        <button type="button" @click="todo.complete = !todo.complete">切換</button>
<!-- {{  }} 可以加入 JS Expression-->
    {{ 1+1 }}
        <hr>
    </div>
</div>

</template>