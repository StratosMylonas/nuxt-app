<template>
  <div v-if="fetching"><p>Loading...</p></div>
  <div v-else>
    <h1>{{ data.post.title }}</h1>
    <h3>{{ data.post.acfTest?.title }}</h3>
    <h3>{{ data.post.acfTest?.content }}</h3>
    <img :src="data.post.featuredImage?.node?.sourceUrl" />
    <div>
      <p class="blogText">{{ data.post.content.replace(/<[^>]+>/g, "") }}</p>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";
import { usePostQuery } from "~/gql/schema";
import { useRoute } from "vue-router";

const route = useRoute();

const { data, fetching } = usePostQuery({
  variables: {
    id: route.params.uri,
  },
});
</script>
