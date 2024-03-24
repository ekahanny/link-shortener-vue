<template>
  <form class="d-flex justify-content-center align-items-center mb-4">
    <div class="form-outline flex-fill">
      <input
        type="text"
        id="addTask"
        class="form-control border-primary-subtle"
        placeholder="Enter the URL"
        required
      />
    </div>
    <button type="submit" class="btn btn-primary ms-2">Shorten</button>
  </form>
</template>

<script>
export default {
  name: "UserInput",
};
</script>
