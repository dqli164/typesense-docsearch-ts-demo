<template>
  <q-page class="row items-center justify-evenly">
    <link
      rel='stylesheet'
      href='https://cdn.jsdelivr.net/npm/typesense-docsearch-css@0.3.0'
    >
    <div class="searchbar"></div>
  </q-page>
</template>

<script setup lang="ts">
import { docsearch } from 'typesense-docsearch.js/dist/esm/docsearch'
docsearch({
  container: '#searchbar',
  typesenseCollectionName: 'faq',
  typesenseServerConfig: {
    nodes: [{
      host: 'localhost',
      port: 8108,
      protocol: 'http'
    }],
    apiKey: 'xyz'
  },
  typesenseSearchParameters: {
    q: 'u',
    query_by: 'url'
  }
})
</script>
