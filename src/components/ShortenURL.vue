<template>
  <div>
    <h4>Shortened URL</h4>
    <div class="flex-container d-flex align-items-baseline">
      <p class="mt-2">http://localhost:8080/</p>
      <font-awesome-icon class="icon ms-2" icon="fa-solid fa-copy" />
    </div>
  </div>
</template>

<script>
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
export default {
  components: {
    FontAwesomeIcon,
  },
};
</script>

<style>
h4 {
  font-family: "Kanit", sans-serif;
  font-weight: 400;
}
</style>
