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
      this.$emit("emitSubmitForm", {
        link: this.link,
      });
      this.link = "";
    },
  },
};
</script>
