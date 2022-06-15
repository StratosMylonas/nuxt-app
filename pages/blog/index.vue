<template>
  <div v-if="fetching">
    <transition name="fade">
      <p>Loading</p>
    </transition>
  </div>
  <div v-else>
    <div v-for="post in data.posts.nodes" :key="post.id">
      <nuxt-link :to="{ path: `/blog/${post.slug}` }">
        <img :src="post.featuredImage?.node?.sourceUrl" />
      </nuxt-link>
      <p>{{ post.title }}</p>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from "vue";
import { useAllPostsQuery } from "~/gql/schema";

const { data, fetching } = useAllPostsQuery();
</script>
