<template>
  <div class="container h-100">
    <div class="row d-flex justify-content-center align-items-center h-100">
      <div class="col col-xl-10">
        <div class="card mt-5">
          <div class="card-body p-5">
            <h1 class="text-center mb-3">URL Shortener</h1>
            <p id="desc" class="text-center fst-italic mb-4">
              The modern, advanced, and privacy-aware URL Shortener built with
              Vue & Bootstrap
            </p>
            <UserInput />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import UserInput from "./components/UserInput.vue";

export default {
  name: "App",
  components: {
    UserInput,
  },
};
</script>

<style>
h1 {
  font-weight: 700;
  color: rgb(69, 116, 216);
}

#desc {
  font-family: "Poppins", sans-serif;
  font-weight: 500;
}

button {
  background-color: rgb(69, 116, 216);
}
</style>
