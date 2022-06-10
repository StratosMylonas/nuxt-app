<template>
  <div v-if="fetching">Loading...</div>
  <div v-else>
    <h1>{{ data.post.title }}</h1>
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
