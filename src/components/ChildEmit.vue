<template>
  <div class="child-emit">
    <h4>Child with emit</h4>
    <p>Value of child:</p> 
    {{ valueEmit }}
    <br>
    <br>
    Value cat: <input type="text"
          @input="$emit('update-value-by-child', valueEmit)"
          v-model="valueEmit.cat">
    <br>
    Value dog:<input type="text"
          
          v-model="valueEmit.dog">    

  </div>
</template>

<script>
export default {
  name: "ChildEmit",
  props: {
    initialValue: Object
  },
  data() {
    return {
      valueEmit: Object.assign({}, this.initialValue)
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
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
