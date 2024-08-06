<script setup>
// import VueComponent from './components/VueComponent.vue';//除了可以匯入元件 也可以匯入js檔案
// 把資料抽出來
//import { ref, reactive } from 'vue';//此堂課完全不會講到reactive，這是給非composition API做使用的，有存在的必要但不建議使用
import { ref } from 'vue';
const text = ref('一句話')
const num = ref(0)//ref可以定義任何型別的資料

// setInterval(() => {
//   num.value = num.value+1
//   console.log(todos.value[0].name);//存取值都要加上.value
// }, 500);

//reactive 的缺點:x
// const data = reactive({
//   name:'卡斯柏'
// })
//1.不能使用純值
//const text1 = reactive('123')
//2.不能重新被賦予
//AJAX 從遠端取回資料就不能蓋過去
// data = {
//   name:'杰倫'
// }



// const todos = ref([//定義vue的資料使用
//   {
//     name:'購買雜貨',
//     dueDate:'2024-07-30',
//     complete:true
// }])


const menu = ref([
  {
    name: '珍珠奶茶',
    description: '香濃奶茶搭配QQ珍珠',
    price: 50,
    storage: 20
  },
  {
    name: '冬瓜檸檬',
    description: '清新冬瓜配上新鮮檸檬',
    price: 45,
    storage: 18
  },
  {
    name: '翡翠檸檬',
    description: '綠茶與檸檬的完美結合',
    price: 55,
    storage: 34
  },
  {
    name: '四季春茶',
    description: '香醇四季春茶，回甘無比',
    price: 45,
    storage: 10
  },
  {
    name: '阿薩姆奶茶',
    description: '阿薩姆紅茶搭配香醇鮮奶',
    price: 50,
    storage: 25
  },
  {
    name: '檸檬冰茶',
    description: '檸檬與冰茶的清新組合',
    price: 45,
    storage: 20
  },
  {
    name: '芒果綠茶',
    description: '芒果與綠茶的獨特風味',
    price: 55,
    storage: 18
  },
  {
    name: '抹茶拿鐵',
    description: '抹茶與鮮奶的絕配',
    price: 60,
    storage: 20
  }
])
const addOne = (item) => {
  item.storage += 1;
  console.log(item.storage)
}




</script>

<template>
<!-- <h1>Vue的資料建構</h1>
<h2>{{ text }}</h2>
<h2>{{ num }}</h2>  -->

  <!-- <h1>目前是 App.vue</h1> -->
  <!-- week 1 HW -->
  <table>
    <thead> 
      <tr>
        <th scope="col">品項</th>
        <th scope="col">描述</th>
        <th scope="col">價格</th>
        <th scope="col">庫存</th>
      </tr>
    </thead>
    <tbody v-for="(item,index) in menu" :key="item.name">
      <tr>
        <td>{{ item.name }}</td>
        <td>{{ item.description }}</td>
        <td>{{ item.price }}</td>
        <button @click="minusOne">-1</button>
        <td>{{ item.storage }}</td>
        <button @click="addOne">+1</button>
      </tr>
    </tbody>
  </table>
  <!-- <h2>{{ text }}</h2> -->
  <!-- <table>
  <thead>
    <tr>
      <th>代辦事項名稱</th>
      <th>到期日</th>
      <th>是否已完成</th>
    </tr>
  </thead>
  <tbody> -->
    <!-- 可以使用v-for來做陣列值的讀取 -->
    <!-- <tr>
      <td>{{todos[0].name}}</td>
      <td>{{todo[0].dueDate}}</td>
      <td>{{todo[0].complete? '是':'否'}}</td>
    </tr>
    <tr v-for="todo in todos" :key="todo.id">
      <td>{{todos.name}}</td>
      <td>{{todo.dueDate}}</td>
      <td>{{todo.complete? '是':'否'}}</td>
    </tr> -->
    <!-- <tr>
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
</table> -->
</template>

<style>

</style>


<!-- <script setup>
// import HelloWorld from './components/HelloWorld.vue'
// import TheWelcome from './components/TheWelcome.vue'
import { ref } from 'vue';
const num = ref(2);
function clickMe(){
  num.value++
}
</script> -->

<!-- <template>
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
</style> -->
