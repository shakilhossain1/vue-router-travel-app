<template>
  <div id="nav">
    <AppLink to="/">Home</AppLink>
    <AppLink
      v-for="destination in destinations"
      :key="destination.id"
      :to="{
        name: 'destination.show',
        params: { id: destination.id, slug: destination.slug },
      }"
    >
      {{ destination.name }}
    </AppLink>
    <AppLink :to="{name: 'protected'}">Dashboard</AppLink>
    <AppLink :to="{name: 'invoices'}">Invoices</AppLink>
    <AppLink to="https://google.com">Google</AppLink>
  </div>
</template>

<script>
import { reactive } from 'vue';
import sourceData from '@/data.json';

export default {
  setup() {
    let destinations = reactive(sourceData.destinations);

    return { destinations };
  },
};
</script>
