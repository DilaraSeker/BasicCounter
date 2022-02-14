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
      count: null,
    };
  },
  
  methods: {
    increment() {
      //this.count++;

      const requestOptions = {
        method: "POST",
        mode: 'cors',
        headers: { "Content-Type":"application/json"},
        body: JSON.stringify({ "operationType":"Increment"})
      };
      fetch("http://localhost:3000/counter", requestOptions)
      .then(response => {
        if (!response.ok) {
          throw new Error(response.error)
        }
        return response.json();
        
      })
      .then(data => (this.count = data.counter));
    },
    decrement() {
      //this.count--;
      const requestOptions = {
      method: "POST",
      mode: 'cors',
      headers: { "Content-Type": "application/json"},
      body: JSON.stringify({ "operationType":"Decrement"})
      };
      fetch("http://localhost:3000/counter", requestOptions)
      .then(response => {
        if (!response.ok) {
          throw new Error(response.error)
        }
        return response.json();
      })
      .then(data => (this.count = data.counter));
    },
  },

  created() {
    fetch("http://localhost:3000/counter")
    .then(response => response.json())
    .then(data => (this.count = data.counter));
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
