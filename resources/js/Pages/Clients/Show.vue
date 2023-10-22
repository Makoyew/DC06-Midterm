<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head } from '@inertiajs/vue3';
import { ref, computed } from 'vue';
import ClientDetails from '@/Components/ClientDetails.vue'; // Import the ClientDetails component
import SalesTable from '@/Components/SalesTable.vue'; // Import the SalesTable component

const props = defineProps({
  client: Object,
  sales: Array,
});
</script>

<template>
    <AuthenticatedLayout>
      <div class="flex items-center justify-center py-8 mx-auto max-w-7xl sm:px-6 lg:px-4">
        <ClientDetails :client="client" />
        <SalesTable :sales="sales" />
      </div>
    </AuthenticatedLayout>
  </template>
