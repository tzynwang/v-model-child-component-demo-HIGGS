<template>
  <input class="input" type="text" :value="componentValue" @input="emitValue" />
</template>

<script>
export default {
  name: "inputComponent",
  props: ["componentValue"],
  methods: {
    emitValue(e) {
      this.$emit("child-input-value-change", e.target.value);
    },
  },
};
</script>
