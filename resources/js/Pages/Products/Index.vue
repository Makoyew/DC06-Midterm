<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head, Link, usePage } from '@inertiajs/vue3';
import Product from '@/Components/Product.vue';


const page = usePage();

const { products } = defineProps(['products']);
</script>

<template>
  <Head title="Products" />

  <AuthenticatedLayout>
    <div class="relative flex justify-end mt-5 mr-40">
      <Link :href="route('product.create')" class="px-4 py-3 text-sm text-white bg-gray-500 rounded-md">
        Add Product
      </Link>
    </div>

    <div class="py-12">
      <div class="mx-auto max-w-7xl sm:px-6 lg:px-8">
        <div class="grid grid-cols-4 gap-4">
          <Product
            v-for="product in products"
            :key="product.id"
            :product="product"
            class="p-4 mb-4 duration-200 transform bg-gray-100 rounded-lg shadow-md cursor-pointer hover:bg-gray-200 hover:scale-105"
          />
        </div>
      </div>
    </div>
  </AuthenticatedLayout>
</template>
