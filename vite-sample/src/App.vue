<!-- <script setup>
// import VueComponent from './components/VueComponent.vue';//除了可以匯入元件 也可以匯入js檔案
// 把資料抽出來
import { ref } from 'vue';
const text = ref('一句話')
const todos = [
  {
    name:'購買雜貨',
    dueDate:'2024-07-30',
    complete:true
}
]
</script>

<template>
  <h1>目前是 App.vue</h1>
  <h2>{{ text }}</h2>
  <table>
  <thead>
    <tr>
      <th>代辦事項名稱</th>
      <th>到期日</th>
      <th>是否已完成</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>{{todos[0].name}}</td>
      <td>2024-07-30</td>
      <td>是</td>
    </tr>
    <tr>
      <td>完成報告</td>
      <td>2024-08-01</td>
      <td>否</td>
    </tr>
    <tr>
      <td>清理房間</td>
      <td>2024-07-28</td>
      <td>是</td>
    </tr>
    <tr>
      <td>計劃假期</td>
      <td>2024-08-05</td>
      <td>否</td>
    </tr>
    <tr>
      <td>處理稅務</td>
      <td>2024-08-10</td>
      <td>否</td>
    </tr>
  </tbody>
</table>
</template>

<style>

</style> -->


<script setup>
// import HelloWorld from './components/HelloWorld.vue'
// import TheWelcome from './components/TheWelcome.vue'
import { ref } from 'vue';
const num = ref(2);
function clickMe(){
  num.value++
}
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <TheWelcome />
  </main>
  <div>
    {{ num }}
    <button type="button" v-on:click = "clickMe">點我</button>
  </div>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
