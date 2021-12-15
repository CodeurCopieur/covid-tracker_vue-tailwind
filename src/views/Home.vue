<template>
  <main v-if="!loading">
    <DataTitle :text="title" :dataDate="dataDate"></DataTitle>
  </main>

  <main v-else class="flex flex-col align-center justify-center text-center">
    <div class="text-gray-500 text-3xl mt-10 mb-6">
      Fetching Data
    </div>
    <img :src="loadingImage" class="w-24 m-auto" alt="">
  </main>
</template>

<script>

  import image from '../assets/hourglass.gif'
  import DataTitle from '../components/DataTitle.vue';
  

  export default {
    name: 'Home',
    components: {
      DataTitle
    },
    data() {
      return {
        loading: true,
        title : 'Global',
        dataDate: '',
        status:{},
        countries: [],
        loadingImage: image
      }
    },
    methods: {
      async fetchCovidData(){
        const res = await fetch('https://api.covid19api.com/summary')
        const data = await res.json()
        return data
      }
    },
    async created() {
      const data = await this.fetchCovidData()

      this.dataDate = data.Date
      this.status = data.Global
      this.countries = data.Countries
      this.loading = false
    }
  }
</script>
