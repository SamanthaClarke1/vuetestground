<template>
  <div>
    <div v-for="(item, i) of reverseitems" :key="i">
      {{ item | testfilter }}
    </div>
  </div>
</template>

<script lang="ts">
  import Vue from 'vue'

  export default Vue.extend({
    props: { },
    data: function() {
      return {
        items: [
          'yaya',
          'yoyo',
          'yayoi'
        ]
      }
    },
    filters: {
      testfilter: function(val: string) {
        return val.toUpperCase().split('').reverse().join('');
      }
    },
    computed: {
      reverseitems: function() {
        return JSON.parse(JSON.stringify(this.$data.items)).reverse();
      }
    }
  });
</script>
