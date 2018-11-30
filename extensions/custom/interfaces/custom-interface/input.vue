<template>
  <div>
    {{message}}
  <input
    type="text"
    :id="name"
    :value="value"
    :readonly="readonly"
    @input="$emit('input', $event.target.value)"
  />
  </div>
</template>

<script>
  import mixin from "@directus/mixins";

  export default {
    mixins: [mixin],
    methods: {
      updateValue(rawValue) {
        if (!rawValue) return;

        let value = rawValue;

        if (this.options.trim) {
          if (!this.value || value.length > this.value.length) {
            value = value.trim();
          }
        }

        this.$emit("input", value);
      }
    },
    data: function() {
      return {
        message: "this is custom interface input2",
        message2: "test2"
      }
    }
  };
</script>

<style lang="scss" scoped>
  input {
    width: 100%;
    max-width: var(--width-medium);
    height:  var(--input-height);
    font-size: 1rem;
    font-weight: 500;
  }

</style>
