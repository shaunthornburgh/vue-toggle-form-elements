<script setup>
import {ref} from "vue";

const framework = ref();
const otherFramework = ref();
</script>

<template>
  <div class="mx-auto max-w-7xl sm:px-6 lg:px-8">
    <form>
      <div class="mt-4">
        <label for="framework" class="block text-sm font-medium leading-6 text-gray-900">Framework</label>
        <select
            id="framework"
            name="framework"
            autocomplete="framework"
            class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 focus:ring-2 focus:ring-inset focus:ring-indigo-600 text-sm"
            v-model="framework"
        >
          <option>Angular</option>
          <option>React</option>
          <option>Vue</option>
          <option>Other</option>
        </select>
      </div>

      <transition name="fade">
        <div class="pt-4" v-show="framework === 'Other'">
          <label for="otherFramework" class="block text-sm font-medium leading-6 text-gray-900">Other framework</label>
          <input
              id="otherFramework"
              name="otherFramework"
              type="text"
              autocomplete="otherFramework"
              class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 text-sm"
              v-model="otherFramework"
          >
        </div>
      </transition>
    </form>
  </div>
</template>

<style>
  .fade-enter-active,
  .fade-leave-active {
    transition: opacity 1s;
  }
  .fade-enter,
  .fade-leave-to {
    opacity: 0;
  }
</style>