<template>
  <div class="space-y-4">
    <div class="pb-10 border-b border-gray-200 mb-10">
      <div>
        <h1 class="inline-block text-3xl font-extrabold text-gray-900 tracking-tight">
          Documentation
        </h1>
      </div>

      <p class="mt-1 text-lg text-gray-500">
        Components library as a Nuxt3 module using <a href="https://github.com/antfu/unocss" target="_blank">UnoCSS</a>.
      </p>
    </div>

    <h2 class="font-bold text-2xl text-tw-gray-900">
      Installation
    </h2>

    <pre class="bg-tw-gray-900 rounded-md text-tw-white px-4">
      <code class="text-sm">
yarn add --dev @nuxthq/ui</code>
    </pre>

    <p>Then, register the module in your `nuxt.config.js`:</p>

    <pre class="bg-tw-gray-900 rounded-md text-tw-white px-4">
      <code class="text-sm">
import { defineNuxtConfig } from 'nuxt3'

export default defineNuxtConfig({
  buildModules: [
    '@nuxthq/ui'
  ]
})</code>
    </pre>

    <p>If you want latest updates, please use `@nuxthq/ui-edge` in your `package.json`:</p>

    <pre class="bg-tw-gray-900 rounded-md text-tw-white px-4">
      <code class="text-sm">
{
  "devDependencies": {
    "@nuxthq/ui": "npm:@nuxthq/ui-edge@latest"
  }
}</code>
    </pre>

    <h2 class="font-bold text-2xl text-tw-gray-900">
      Options
    </h2>

    <p>- `primary`</p>

    <p>Define the primary variant. Defaults to `indigo`. You can specify your own object of colors like here:</p>

    <p class="font-medium">
      Example:
    </p>

    <pre class="bg-tw-gray-900 rounded-md text-tw-white px-4">
      <code class="text-sm">
import { defineNuxtConfig } from 'nuxt3'

export default defineNuxtConfig({
  buildModules: [
    '@nuxthq/ui'
  ],
  ui: {
    primary: 'blue'
  }
})</code>
    </pre>

    <p>- `prefix`</p>

    <p>Define the prefix of the imported components. Defaults to `u`.</p>

    <p class="font-medium">
      Example:
    </p>

    <pre class="bg-tw-gray-900 rounded-md text-tw-white px-4">
      <code class="text-sm">
import { defineNuxtConfig } from 'nuxt3'

export default defineNuxtConfig({
  buildModules: [
    '@nuxthq/ui'
  ],
  ui: {
    prefix: 'tw'
  }
})</code>
    </pre>

    <NuxtLink to="/examples" class="font-bold text-2xl text-tw-gray-900 hover:underline block">
      Examples
    </NuxtLink>
  </div>
</template>