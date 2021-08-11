<template>
  <div class="name">{{ name }}</div>
  <div>{{ greeting(name) }}</div>
  <div>{{ greet }}</div>
  <div>{{ user }}</div>
  <div>{{ city }}</div>
  <button class="btn btn-primary" @click="updateName">Click</button>
</template>

<script>
import { ref, reactive } from "vue";

export default {
  setup() {
    const name = ref("Titu Coder");
    const city = ref({
      name: "seoul",
    });
    //reactive는 obejct, array만 사용 가능
    const user = reactive({
      id: 1,
    });

    const greeting = (name) => {
      return "hello, " + name;
    };

    const greet = greeting(name.value);

    const consoleLog = () => {
      console.log("hello world");
    };

    const updateName = () => {
      name.value = "Titu";
      city.value.name = "Paris";
      user.id = 2;
    };

    return {
      name,
      greeting,
      greet,
      consoleLog,
      updateName,
      user,
      city,
    };
  },
};
</script>

<style>
.name {
  color: red;
}
</style>