<script setup>
import { computed, defineProps, inject } from 'vue';

const props = defineProps({
  client: Object,
  sales: Array,
});

const totalAmount = computed(() => {
  return props.sales.reduce((sum, obj) => sum + (obj.amount || 0), 0);
});

const darkTheme = inject('darkTheme');
</script>


<template>
    <div :class="{ 'filter invert': darkTheme }" class="w-1/2 ml-10">
      <div class="bg-white dark:bg-[#1f1f1f] overflow-hidden shadow-sm sm:rounded-lg p-8">
        <h3 :class="{ 'text-gray-700': !darkTheme, 'text-black': darkTheme }" class="mb-2 text-xl font-semibold text-gray-700 dark:text-gray-50">Sales Transactions</h3>
        <table class="w-full border-collapse">
          <thead>
            <tr :class="{ 'text-gray-700': !darkTheme, 'text-black': darkTheme }"    class="bg-gray-100 dark:bg-purple-600 dark:text-white">
              <th class="px-4 py-2 text-left">Date</th>
              <th class="px-4 py-2 text-left">Cash/Credit</th>
              <th class="px-4 py-2 text-left">Total</th>
            </tr>
          </thead>
          <tbody>
            <tr :class="{ 'text-gray-700': !darkTheme, 'text-black': darkTheme }" v-for="sale in sales" :key="sale.id" class="border-b border-gray-200 dark:border-gray-600">
              <td :class="{ 'text-gray-700': !darkTheme, 'text-black': darkTheme }" class="px-4 py-2 dark:text-white">{{ sale.date }}</td>
              <td :class="{ 'text-gray-700': !darkTheme, 'text-black': darkTheme }" class="px-4 py-2 dark:text-white">{{ sale.is_credit ? 'Credit' : 'Cash' }}</td>
              <td :class="{ 'text-gray-700': !darkTheme, 'text-black': darkTheme }" class="px-4 py-2 dark:text-white">{{ sale.amount }}</td>
            </tr>
            <tr>
              <td colspan="2" class="px-4 py-2 font-semibold text-right dark:text-white">Sum:</td>
              <td class="px-4 py-2 text-xl font-semibold text-center dark:text-white">{{ totalAmount }}</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </template>
