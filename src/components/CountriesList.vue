<template>
  <div>
      <select @change="handleChange">
          <option v-for="(country, index) in countries" :country="country" :key="index">{{country.name}}</option>
      </select>
  </div>
</template>

<script>
import {eventBus} from '@/main.js';

export default {
    name: 'countries-list',
    props: ['countries'],
    methods: {
        handleChange: function (event) {
            eventBus.$emit("country-select", event.target.value)
        }
    },
    components: {
   
    }
}
</script>

<style>

</style>