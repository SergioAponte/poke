<!-- Please remove this file from your project -->
<template>
  <div class="relative flex items-top justify-center min-h-screen bg-gray-100 sm:items-center sm:pt-0">
    <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.1.2/dist/tailwind.min.css" rel="stylesheet">
    <div class="max-w-4xl mx-auto sm:px-6 lg:px-8">
      <a class="flex justify-center pt-8 sm:pt-0" href="https://nuxtjs.org" target="_blank">
        <img src="data:image/png;base64,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" alt="">
      </a>
      <div class="mt-8 bg-white overflow-hidden shadow sm:rounded-lg p-6">
        <h2 class="text-2xl leading-7 font-semibold">
          Welcome to your Nuxt Application
        </h2>
        <p class="mt-3 text-gray-600">
          We recommend you take a look at the <a href="https://nuxtjs.org" target="_blank" class="button--doc text-green-500 hover:underline">Nuxt Documentation</a>, whether you are new or have previous experience with the framework.<br>
        </p>
        <p class="mt-4 pt-4 text-gray-800 border-t border-dashed">
          To get started, remove <code class="bg-gray-100 text-sm p-1 rounded border">components/Tutorial.vue</code> and start coding in <code class="bg-gray-100 text-sm p-1 rounded border">pages/index.vue</code>. Have fun!
        </p>
      </div>
      <div class="flex justify-center pt-4 space-x-2">
        <a href="https://github.com/nuxt/nuxt.js" target="_blank"><svg
          class="w-6 h-6 text-gray-600 hover:text-gray-800 button--github"
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          aria-hidden="true"
          role="img"
          width="32"
          height="32"
          preserveAspectRatio="xMidYMid meet"
          viewBox="0 0 24 24"
        ><path d="M12 2.247a10 10 0 0 0-3.162 19.487c.5.088.687-.212.687-.475c0-.237-.012-1.025-.012-1.862c-2.513.462-3.163-.613-3.363-1.175a3.636 3.636 0 0 0-1.025-1.413c-.35-.187-.85-.65-.013-.662a2.001 2.001 0 0 1 1.538 1.025a2.137 2.137 0 0 0 2.912.825a2.104 2.104 0 0 1 .638-1.338c-2.225-.25-4.55-1.112-4.55-4.937a3.892 3.892 0 0 1 1.025-2.688a3.594 3.594 0 0 1 .1-2.65s.837-.262 2.75 1.025a9.427 9.427 0 0 1 5 0c1.912-1.3 2.75-1.025 2.75-1.025a3.593 3.593 0 0 1 .1 2.65a3.869 3.869 0 0 1 1.025 2.688c0 3.837-2.338 4.687-4.563 4.937a2.368 2.368 0 0 1 .675 1.85c0 1.338-.012 2.413-.012 2.75c0 .263.187.575.687.475A10.005 10.005 0 0 0 12 2.247z" fill="currentColor" /></svg></a>
        <a href="https://twitter.com/nuxt_js" target="_blank"><svg
          class="w-6 h-6 text-gray-600 hover:text-gray-800"
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          aria-hidden="true"
          role="img"
          width="32"
          height="32"
          preserveAspectRatio="xMidYMid meet"
          viewBox="0 0 24 24"
        ><path d="M22.46 6c-.77.35-1.6.58-2.46.69c.88-.53 1.56-1.37 1.88-2.38c-.83.5-1.75.85-2.72 1.05C18.37 4.5 17.26 4 16 4c-2.35 0-4.27 1.92-4.27 4.29c0 .34.04.67.11.98C8.28 9.09 5.11 7.38 3 4.79c-.37.63-.58 1.37-.58 2.15c0 1.49.75 2.81 1.91 3.56c-.71 0-1.37-.2-1.95-.5v.03c0 2.08 1.48 3.82 3.44 4.21a4.22 4.22 0 0 1-1.93.07a4.28 4.28 0 0 0 4 2.98a8.521 8.521 0 0 1-5.33 1.84c-.34 0-.68-.02-1.02-.06C3.44 20.29 5.7 21 8.12 21C16 21 20.33 14.46 20.33 8.79c0-.19 0-.37-.01-.56c.84-.6 1.56-1.36 2.14-2.23z" fill="currentColor" /></svg></a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'NuxtTutorial'
}
</script>
