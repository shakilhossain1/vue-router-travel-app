<template>
  <div class="card">
    <img :src="`/images/${expericne.image}`" :alt="expericne.name" />
    <span class="card__text">
      {{ expericne.name }}
    </span>
  </div>
</template>

<script>
export default {
  props: {
    expericne: { required: true, type: Object },
  },
};
</script>
