<template>
    <div>
        <p>{{count}}</p>
        <button @click="decrement">DECREMENT</button>
        <button @click="increment">INCREMENT</button>
    </div>
</template>

<script>
export default {
  name: "Counter",
  data() {
    return {
      count: 0
    };
  },
  methods: {
    increment() {
      this.count++;
    },
    decrement() {
      this.count--;
    }
  }
};
</script>

<style scoped>
h1,
h2 {
  font-weight: normal;
}
button{
  color: #b94283;
  margin-left: 10px;
}

</style>
