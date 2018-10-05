<template>
  <div class="hello">
    <h1>{{ msg }}</h1>    
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  async created(){
    const config = {
      headers: {
        Authorization: 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoibWlndWVsIn0.XnBRt8Lo5aG0UjWWgPi683fgWi3yBNh4gZVh9YW-9Fg',
      } 
    }
    const api = process.env.NODE_ENV === 'production' ? 'http://756d1119-c231-4419-aa2e-733226de1c62.clouding.host:8089/car' : 'http://localhost:8089/car'
    const res = await axios.post(api, 
      {
      "name": "miguelito",
      "contact": {
        "email": "miguel.alarcos@gmail.com"
        }
      },
      config
    )
    console.log(res)
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
