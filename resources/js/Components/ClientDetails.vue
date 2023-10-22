<script setup>
import { defineProps, inject } from 'vue';

const props = defineProps({
  client: Object,
});

const darkTheme = inject('darkTheme');
</script>

<template>
    <div :class="{ 'filter invert': darkTheme }" class="w-80">
      <div class="bg-white dark:bg-[#1f1f1f] overflow-hidden shadow-sm sm:rounded-lg p-8">
        <h2 :class="{ 'text-gray-700': !darkTheme, 'text-black': darkTheme }" class="mb-4 text-3xl font-semibold text-gray-900 dark:text-white">
          {{ client.first_name }} {{ client.last_name }}
        </h2>
        <h3 :class="{ 'text-gray-700': !darkTheme, 'text-black': darkTheme }" class="mb-2 text-xl font-semibold text-gray-700 dark:text-gray-50">Client Details</h3>
        <div class="mb-4">
          <p :class="{ 'text-gray-700': !darkTheme, 'text-black': darkTheme }" class="text-sm font-semibold text-gray-700 dark:text-gray-50">Address:</p>
          <p :class="{ 'text-gray-700': !darkTheme, 'text-black': darkTheme }" class="text-sm font-light text-gray-700 dark:text-gray-50">{{ client.address }}</p>
        </div>
        <div class="mb-4">
          <p :class="{ 'text-gray-700': !darkTheme, 'text-black': darkTheme }" class="text-sm font-semibold text-gray-700 dark:text-gray-50">Phone:</p>
          <p :class="{ 'text-gray-700': !darkTheme, 'text-black': darkTheme }" class="text-sm font-light text-gray-700 dark:text-gray-50">{{ client.phone }}</p>
        </div>
        <div>
          <p :class="{ 'text-gray-700': !darkTheme, 'text-black': darkTheme }" class="text-sm font-semibold text-gray-700 dark:text-gray-50">Credit Limit:</p>
          <p :class="{ 'text-gray-700': !darkTheme, 'text-black': darkTheme }" class="text-sm font-light text-gray-700 dark:text-gray-50">{{ client.credit_limit }}</p>
        </div>
      </div>
    </div>
  </template>
