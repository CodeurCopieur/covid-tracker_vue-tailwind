<template>
  <select 
    @change="onChange()"
    class="form-select mt-10 block w-full border p-3 rounded"
    v-model="selected">
    <option value="0">Select Pays</option>
    <option v-for="country in countries" :key="country.ID" :value="country.ID">{{country.Country}}</option>
  </select>
</template>

<script>

  import { ref } from 'vue';

  export default {
    name: 'CountrySelect',
    props: ['countries'],
    setup({countries}, {emit}) {
      const selected = ref(0);

      return {
        selected,
        onChange() {
          const country = countries.find(item => item.ID === selected.value)
          console.log(country);
          emit('get-country', country)
        }
      }
    }
  }
</script>
