<template>
  <div class="experiences">
    <div class="card">
      <img :src="`/images/${experiences.image}`" :alt="experiences.name" />
      <span class="card__text">
        {{ experiences.name }}
      </span>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    experiences: { type: Object, required: true },
  },
};
</script>
