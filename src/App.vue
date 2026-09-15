<script setup>
import { ref } from 'vue';
import ImageRemover from './components/ImageRemover.vue';
import VideoRemover from './components/VideoRemover.vue';

const tab = ref('image'); // 'image' | 'video'
</script>

<template>
  <main class="flex-grow w-full min-h-screen bg-theme-light dark:bg-theme-dark flex flex-col items-center justify-start px-4 py-12">
    
    <!-- 1. اسم الأداة فقط -->
    <h1 class="text-3xl md:text-5xl font-extrabold mb-4 text-slate-900 dark:text-white tracking-tight text-center">
      Gemini 
      <span class="text-transparent bg-clip-text bg-gradient-to-r from-brand-primary via-brand-secondary to-brand-accent">
        Watermark Remover
      </span>
    </h1>
    
    <p class="text-slate-500 dark:text-slate-400 max-w-xl mx-auto font-medium text-base md:text-lg mb-8 text-center">
      Remove the visible ✦ sparkle watermark from Google Gemini AI images and Veo videos.
    </p>

    <!-- 2. أزرار التبديل بين الصور والفيديو -->
    <div class="mb-8">
      <div class="inline-flex p-1.5 rounded-2xl bg-gray-100 dark:bg-theme-cardDark border border-gray-200 dark:border-gray-800">
        <button
          @click="tab = 'image'"
          :class="[
            'flex items-center gap-2 px-6 py-2.5 rounded-xl font-bold text-sm transition-all',
            tab === 'image' ? 'bg-white dark:bg-gray-800 text-brand-primary shadow-sm' : 'text-slate-500 dark:text-slate-400 hover:text-slate-700 dark:hover:text-slate-200'
          ]"
        >
          <iconify-icon icon="ph:image-bold" width="18"></iconify-icon> Image
        </button>
        <button
          @click="tab = 'video'"
          :class="[
            'flex items-center gap-2 px-6 py-2.5 rounded-xl font-bold text-sm transition-all',
            tab === 'video' ? 'bg-white dark:bg-gray-800 text-brand-primary shadow-sm' : 'text-slate-500 dark:text-slate-400 hover:text-slate-700 dark:hover:text-slate-200'
          ]"
        >
          <iconify-icon icon="ph:video-camera-bold" width="18"></iconify-icon> Video
        </button>
      </div>
    </div>

    <!-- 3. صندوق الرفع والأداة فقط -->
    <div class="w-full max-w-4xl">
      <ImageRemover v-show="tab === 'image'" />
      <VideoRemover v-show="tab === 'video'" />
    </div>

  </main>
</template>
