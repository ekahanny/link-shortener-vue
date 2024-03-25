<template>
  <div>
    <h5>Shortened URL</h5>
    <div
      v-if="URL && URL.link"
      class="flex-container d-flex align-items-baseline"
    >
      <p id="shortenedURL">{{ URL.link }}</p>
      <font-awesome-icon
        ref="copyButton"
        class="icon ms-2"
        icon="fa-solid fa-copy"
        data-clipboard-text="{{ URL.link }}"
        @click="copyToClipboard"
      />
    </div>
  </div>
</template>

<script>
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import Clipboard from "clipboard";

export default {
  name: "ShortenURL",
  components: {
    FontAwesomeIcon,
  },
  props: {
    URL: Object,
  },
  mounted() {
    new Clipboard(this.$refs.copyButton);
  },
  methods: {
    copyToClipboard() {
      const textToCopy = this.URL.link;
      navigator.clipboard
        .writeText(textToCopy)
        .then(() => {
          window.alert("URL copied!");
        })
        .catch((err) => {
          console.error("Failed to copy text: ", err);
        });
    },
  },
};
</script>

<style>
h4 {
  font-family: "Kanit", sans-serif;
  font-weight: 400;
}
</style>
