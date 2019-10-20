<template>
  <div id="app" class="container">

    <div class="row mb-5">
      <div class="col-12">

        <h4>Parent</h4>
        <table class="table">
          <tr class="p-2">
            <td><p>Value with object as prop (reference) of parent:</p></td>
            <td>{{ valueReference }}</td>
          </tr>

          <tr class="p-2">
            <td><p>Value with emit of parent::</p></td>
            <td>{{ valueEmit }}</td>
          </tr>
        </table>  

      </div>
    </div>

    <div class="row">

      <div class="col-6">
        <ChildReference :valueReference="valueReference">
        </ChildReference>
      </div>

      <div class="col-6">
        <ChildEmit :initialValue="valueEmit"
                  @update-value-by-child="updateParentValue">
        </ChildEmit>
      </div>

    </div>

   

  </div>
</template>

<script>
import ChildReference from "./components/ChildReference";
import ChildEmit from "./components/ChildEmit";

export default {
  name: "App",
  components: {
    ChildReference,
    ChildEmit
  },
  data() {
    return {
      valueReference: {},
      valueEmit: {}
    }
  },
  methods: {
    updateParentValue(newValue) {
      console.log("new value", newValue)
      this.valueEmit = newValue;
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
