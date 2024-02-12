<template>
    <div>
        <label for="username">USERNAME : </label>
      <input type="text" v-model="username" placeholder="Enter Username" />
      <p v-if="!isUserAvailable">{{ username }} is already taken.</p>
      <p v-else > {{ username}} available!</p>
    </div>
  </template>
  <script setup>
  import { ref, computed } from 'vue';

      const existingUsernames = ref(['john', 'doe', 'jane']);
  
      const username = ref('');
  
      const isUserAvailable = computed(() => {
        // Check if entered username exists in the list
        return !existingUsernames.value.includes(username.value.toLowerCase());
      });
  
</script>
<style>

input:focus{
  outline: none;

}
p{

}

</style>