<template>
  <div class="no-wrap">{{ displayValue }}</div>
</template>

<script>
  import mixin from "@directus/mixins";


  export default {
    mixins: [mixin],

    created: function() {
         console.log('created interface-example');
    },


    computed: {
      displayValue() {
        let value = this.value;

        if (this.options.formatValue) {
          value = this.$helpers.formatTitle(value);
        }

        return value;
      }
    }
  };
</script>

<style lang="scss" scoped>
  .test {
    width: 100%;
  }
</style>
