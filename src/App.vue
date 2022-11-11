<script>
import axios from "axios";
import {store} from "./store";
import AppLoading from "./components/AppLoading.vue";
import AppHeader from "./components/AppHeader.vue"; 
import MainCharactersList from "./components/MainCharactersList.vue";

export default{
  components: {
    AppHeader,
    AppLoading,
    MainCharactersList
  },
  data() {
    return {
      store
    }
  },
  created() {
    // Prima di iniziare la chiamata, mettiamo loading a true
    this.store.loading = true;
    axios.get("https://www.breakingbadapi.com/api/characters").then((resp) => {
      this.store.characters = resp.data;
      console.log(this.store.characters);
      // resettiamo loading a false poichè i dati sono arrivati
      this.store.loading = false;
    })
  }
}
</script>

<template>
<AppHeader />
<AppLoading />
<MainCharactersList />
</template>

<style lang="scss" scoped>
@use "./styles/general.scss" as*
</style>
