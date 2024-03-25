<template>
  <form
    class="d-flex justify-content-center align-items-center mb-4"
    @submit.prevent="submit"
  >
    <div class="form-outline flex-fill">
      <input
        type="text"
        id="addURL"
        class="form-control border-primary-subtle"
        placeholder="Enter the URL"
        required
        v-model="link"
      />
    </div>
    <button type="submit" class="btn btn-primary ms-2">Shorten</button>
  </form>
</template>

<script>
export default {
  name: "UserInput",
  data() {
    return {
      link: "",
    };
  },
  methods: {
    submit: function () {
      const longURL = this.link;
      const requestBody = {
        long_url: longURL,
      };

      fetch("https://api-ssl.bitly.com/v4/shorten", {
        method: "POST",
        headers: {
          Authorization: "Bearer 84bd16d1579d48609bca8e04ef7d2dbc40d370ab",
          "Content-Type": "application/json",
        },
        body: JSON.stringify(requestBody),
      })
        .then((response) => response.json())
        .then((data) => {
          if (data.link) {
            this.$emit("emitShortenedURL", data.link);
          } else {
            console.error("Error shortening URL: ", data);
          }
        })
        .catch((error) => console.error("Error fetching Bitly API: ", error));

      this.link = "";
    },
  },
};
</script>
