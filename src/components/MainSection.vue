<template>
  <section class="min-h-screen bg-[#070D19] py-12 px-4 sm:px-6 lg:px-8 font-sans selection:bg-[#1DB4EF] selection:text-white">
    <div class="max-w-7xl mx-auto">
      <div class="flex justify-between items-end mb-10">
        <h2 class="text-3xl font-extrabold text-transparent bg-clip-text bg-gradient-to-r from-white to-gray-400">
          New Arrivals
        </h2>
      </div>

      <div v-if="loading" class="flex justify-center items-center py-32">
        <div class="relative w-16 h-16">
          <div class="absolute inset-0 rounded-full border-t-2 border-[#1DB4EF] animate-spin"></div>
          <div class="absolute inset-2 rounded-full border-r-2 border-white/30 animate-spin animate-reverse"></div>
        </div>
      </div>

      <div v-else-if="error" class="text-red-400 text-center py-12 bg-red-950/20 backdrop-blur-md rounded-2xl border border-red-500/20">
        {{ error }}
      </div>

      <div v-else class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-8">
        <div
          v-for="product in products"
          :key="product.id"
          class="group flex flex-col bg-[#111826]/40 backdrop-blur-xl border border-white/5 rounded-2xl overflow-hidden hover:-translate-y-2 hover:border-[#1DB4EF]/50 hover:shadow-[0_10px_40px_-10px_rgba(29,180,239,0.25)] transition-all duration-500 ease-out cursor-pointer"
        >
          <div class="relative h-64 p-6 flex items-center justify-center bg-gradient-to-b from-white/5 to-transparent overflow-hidden">
            <div class="absolute inset-0 bg-[#1DB4EF]/20 opacity-0 group-hover:opacity-100 transition-opacity duration-500 blur-3xl rounded-full scale-150 transform -translate-y-10"></div>
            
            <img
              :src="product.thumbnail"
              :alt="product.title"
              class="relative z-10 max-h-full max-w-full object-contain drop-shadow-[0_15px_25px_rgba(0,0,0,0.6)] group-hover:scale-110 transition-transform duration-500 ease-out"
              loading="lazy"
            />
            
            <div class="absolute top-4 left-4 flex flex-col gap-2 z-20">
              <span 
                v-if="product.stock < 20" 
                class="bg-red-500/80 backdrop-blur-md text-white text-[10px] uppercase font-bold tracking-widest px-3 py-1.5 rounded-full shadow-lg"
              >
                Low Stock
              </span>
            </div>
          </div>

          <div class="p-6 flex flex-col flex-grow relative z-10 bg-gradient-to-t from-[#0d131f] to-transparent">
            <div class="flex justify-between items-center mb-3">
              <span class="text-xs text-gray-400 font-semibold tracking-wider uppercase">{{ product.brand }}</span>
              <div class="flex items-center bg-white/5 px-2 py-1 rounded-md backdrop-blur-sm border border-white/10">
                <span class="text-yellow-400 text-xs mr-1.5">★</span>
                <span class="text-gray-200 text-xs font-medium">{{ product.rating }}</span>
              </div>
            </div>
            
            <h3 class="text-lg font-bold text-gray-100 mb-2 line-clamp-1 group-hover:text-[#1DB4EF] transition-colors duration-300" :title="product.title">
              {{ product.title }}
            </h3>
            
            <p class="text-sm text-gray-400 mb-6 line-clamp-2 leading-relaxed">
              {{ product.description }}
            </p>

            <div class="mt-auto flex items-center justify-between pt-5 border-t border-white/5">
              <div class="flex flex-col">
                <span class="text-xs text-gray-500 line-through mb-0.5" v-if="product.discountPercentage">
                  ${{ Math.round(product.price / (1 - product.discountPercentage / 100)) }}
                </span>
                <span class="text-2xl font-black text-white">${{ product.price }}</span>
              </div>
              
              <button class="flex items-center justify-center w-10 h-10 bg-white/5 hover:bg-[#1DB4EF] text-white rounded-xl border border-white/10 hover:border-transparent transition-all duration-300 group-hover:shadow-[0_0_15px_rgba(29,180,239,0.5)]">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 4v16m8-8H4" />
                </svg>
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue';

interface Product {
  id: number;
  title: string;
  description: string;
  brand: string;
  price: number;
  rating: number;
  stock: number;
  thumbnail: string;
  discountPercentage?: number;
}

interface DummyJsonProductResponse {
  products: Product[];
  total: number;
  skip: number;
  limit: number;
}

const products = ref<Product[]>([]);
const loading = ref<boolean>(true);
const error = ref<string | null>(null);

const fetchProducts = async () => {
  try {
    loading.value = true;
    error.value = null;
    
    const response = await fetch('https://dummyjson.com/products/category/smartphones?limit=8');
    
    if (!response.ok) {
      throw new Error(`Error: ${response.status} - Failed to fetch products`);
    }
    
    const data: DummyJsonProductResponse = await response.json();
    products.value = data.products;
    
  } catch (err) {
    error.value = err instanceof Error ? err.message : 'An unknown error occurred while loading products.';
  } finally {
    loading.value = false;
  }
};

onMounted(() => {
  fetchProducts();
});
</script>