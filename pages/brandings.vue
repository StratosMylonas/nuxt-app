<template>
  <div v-if="fetching"><p>Loading...</p></div>
  <div v-else>
    <div v-for="post in data.brandings.nodes" :key="post.id">
      <h1>{{ post.title }}</h1>
      <p>{{post.content.replace(/<[^>]+>/g, "")}}</p>
      <br>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from "vue";
import { useAllBrandingsQuery } from "~/gql/schema";

const { data, fetching } = useAllBrandingsQuery();
</script>
