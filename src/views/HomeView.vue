<template>
  <div class="home">
    <div class="container mx-auto">
      <div class="flex flex-wrap justify-between">
        <div class="w-1/5" v-for="photo of photos.results" :key="photo.id">
          <img class="w-full h-full object-cover" :src="photo.urls.regular" alt="" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "HomeView",
  data() {
    return {
      photos: [],
    };
  },
  async mounted() {
    let res = await axios.get(
      "https://api.unsplash.com/search/photos?query={'dogs'}&client_id=UxQcyiv7djwaIznmB6G73bYjldVCcICcUT4HZpscGcI"
    );
    this.photos = res.data;
  },
};
</script>
