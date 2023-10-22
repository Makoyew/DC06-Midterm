<script>
import TextInput from '@/Components/TextInput.vue';
import InputLabel from '@/Components/InputLabel.vue';
import { inject } from 'vue';

const darkTheme = inject('darkTheme');

export default {
  components: {
    TextInput,
    InputLabel,
  },
};
</script>

<template>
    <div :class="{ 'filter invert': darkTheme }" class="bg-white shadow-sm sm:rounded-lg">
      <div class="p-6">
        <h2 class="text-2xl font-semibold text-gray-800">Product Details</h2>

        <div class="grid grid-cols-2 gap-6 mt-6">
          <div>
            <InputLabel for="product" value="Product Name" />
            <TextInput type="text" class="w-full" id="product" />
          </div>

          <div>
            <InputLabel for="brand" value="Brand" />
            <TextInput type="text" class="w-full" id="brand" />
          </div>

          <div class="col-span-2">
            <InputLabel for="description" value="Description" />
            <textarea
              id="description"
              class="w-full mt-2 border-gray-300 rounded-lg shadow-sm focus:border-indigo-500 focus:ring-indigo-500"
            ></textarea>
          </div>

          <div>
            <InputLabel for="retail_price" value="Retail Price" />
            <TextInput type="number" class="w-full" id="retail_price" />
          </div>

          <div>
            <InputLabel for="qty_stock" value="Quantity in Stock" />
            <TextInput type="number" class="w-full" id="qty_stock" />
          </div>

          <div class="col-span-2">
            <InputLabel for="category" value="Category" />
            <select
              id="category"
              class="w-full border-gray-300 rounded-lg shadow-sm focus:border-indigo-500 focus:ring-indigo-500"
            >
              <option value="" selected>Select a Category</option>
              <!-- Add category options here -->
            </select>
          </div>
        </div>

        <div class="mt-6">
          <p class="text-xl font-semibold text-gray-800">Add Product Images</p>

          <label for="dropzone-file" class="flex items-center justify-center w-full h-40 mt-3 border-2 border-gray-300 border-dashed rounded-lg cursor-pointer">
            <div class="text-gray-500">
              <svg class="w-12 h-12 mb-3" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 20 16" stroke="currentColor">
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M13 13h3a3 3 0 0 0 0-6h-.025A5.56 5.56 0 0 0 16 6.5 5.5 5.5 0 0 0 5.207 5.021C5.137 5.017 5.071 5 5 5a4 4 0 0 0 0 8h2.167M10 15V6m0 0L8 8m2-2 2 2"
                />
              </svg>
              <p class="text-lg font-semibold">Click to upload</p>
              <p class="text-sm text-gray-500">or drag and drop files here (max. 800x400px)</p>
            </div>
            <input id="dropzone-file" type="file" class="hidden" />
          </label>
        </div>

        <div class="mt-6">
          <button class="px-4 py-2 text-white bg-indigo-600 rounded-md hover:bg-indigo-700">
            Save Product
          </button>
        </div>
      </div>
    </div>
  </template>
