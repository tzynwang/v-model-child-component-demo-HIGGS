<template>
  <div id="app">
    <div>
      data 2-way binding in component:
      <span class="highlight">{{ componentValue }}</span>
    </div>
    <inputComponent
      class="input"
      :component-value="componentValue"
      @child-input-value-change="childInputValueChange"
      autofocus
    />
  </div>
</template>

<script>
import inputComponent from "./components/inputComponent.vue";

export default {
  name: "App",
  components: {
    inputComponent,
  },
  data() {
    return {
      componentValue: "hello world",
    };
  },
  methods: {
    childInputValueChange(value) {
      this.componentValue = value;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.highlight {
  color: red;
}

.input {
  margin-top: 1rem;
  padding: 0.5rem;

  outline: none;
  border: 1px solid #2c3e50;

  font-family: inherit;
  font-size: inherit;
}
</style>
