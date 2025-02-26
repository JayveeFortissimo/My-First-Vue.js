<template>
  <!--V- Directive-->
  <div v-if="Checking">
    <HomePage />
  </div>
  <!-------------For Executing of arrays parang Ano sya Array methods Like that------------------->
  <!--V-for Directive and Looping-->
  <div>
    <p v-for="array in arrayOfobject" :key="array">
      {{ array.name }}, {{ array.id }}
    </p>
  </div>

  <!--V-bind Directive-->
  <a v-bind:href="links">google</a>
  <div
    v-bind:style="{
      height: '2rem',
      borderRadius: '20px',
      border: '1px solid black',
    }"
  >
    <p>Helllo</p>
  </div>

  <!---ShortCut of V-bind----->
  <p :class="hello"></p>

  <!-------------------------->

  <!--V-on Directives Events and methods-->
  <!--------Event================-->
  <button @click="count++">Click</button>
  {{ count }}

  <input v-model="names" />
  <!--Same lang den sa V-on Diretives pero mas gamit tong event na claick-->
  {{ names }}

  <div>
    <p>username</p>
    <input
      type="text"
      :value="AllData.username"
      @input="userDatas('username', $event.target.value)"
    />
  </div>

  <div>
    <p>address</p>
    <input
      type="text"
      :value="AllData.address"
      @input="userDatas('address', $event.target.value)"
    />
  </div>

  <div>
    <p>Age</p>
    <input
      type="number"
      :value="AllData.age"
      @input="userDatas('age', $event.target.value)"
    />
  </div>
  {{ AllData}}
</template>


<script>
import HomePage from "./components/HomePage.vue";

export default {
  data() {
    return {
      count: 0,
      arrayOfobject: [
        { id: 1, name: "Jayvee" },
        { id: 2, name: "Mj" },
        { id: 3, name: "Anthony" },
      ],
      links: "https://www.google.com/",
      names: "",

      AllData: {
        username: "",
        address: "",
        age: 0,
      },
    };
  },
  methods: {
    userDatas(type, data) {
    this.AllData[type] = data; // Update the specific property directly
  }
  },
};
</script>
