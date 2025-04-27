<template>
  <main class="form-signin w-25 m-auto mt-5">
    <form>
      <img
        :src="logo"
        alt="logo"
        class="w-50"
        style="width: 100px; cursor: pointer"
        @click="toHomeHandler"
      />
      <h1 class="h3 mb-3 fw-normal mt-3">Register</h1>

      <Input :label="'Name'" :type="'text'" :placeholder="'name'" />

      <Input :label="'Email address'" :type="'email'" :placeholder="'email'" />

      <Input :label="'Password'" :type="'password'" :placeholder="'password'" />

      <Button type="submit" :disabled="isLoading" @click="submitHandler"
        >Register</Button
      >
    </form>
  </main>
</template>
<script>
import { logo } from "../constants";
export default {
  data() {
    return {
      logo,
    };
  },
  computed: {
    isLoading() {
      return this.$store.state.auth.isLoading;
    },
  },
  methods: {
    submitHandler(e) {
      e.preventDefault();
      this.$store.dispatch("register");
    },
  },
};
</script>
<style></style>
