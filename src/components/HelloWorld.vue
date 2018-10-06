<template>
  <div class="hello">
    <h1>{{ msg }}</h1>   
    <number-input v-model="age"></number-input>
    <md-button @click="post" class="md-primary">Post</md-button>
    <span class="md-error red">{{$store.state.errors.age}}</span>
  </div>
</template>

<script>
import numberInput from '@/components/numberInput'

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data(){
    return {
    }
  },
  computed: {
    age: {
        get() {
            return this.$store.state.form.age
        },
        set(value) {
            this.$store.commit('setAge', value)
        }
    }
  },
  components: {numberInput},
  methods: {
    post(){
      this.$store.dispatch('post')
    }
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
.red{
  color: red;
}
</style>
