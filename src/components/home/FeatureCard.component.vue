<template>
  <v-card class="card">
    <v-card-title>{{ content.title }}</v-card-title>
    <v-card-text>{{ content.text }}</v-card-text>
    <div class="icon-container">
      <v-icon x-large class="icon" color="primary">{{ content.icon }}</v-icon>
    </div>
  </v-card>
</template>

<script lang="ts">
import { Component, Vue, Prop } from "vue-property-decorator";

interface FeatureCardContent {
  title: string;
  text: string;
  icon: string;
}

@Component
export default class FeatureCard extends Vue {
  @Prop({ required: true }) content!: FeatureCardContent;
}

export { FeatureCardContent };
</script>

<style scoped>
.card {
  padding: 1rem;
  width: 25rem;
}

.icon-container {
  width: 100%;
  display: flex;
  justify-content: center;
}

.icon {
  padding-bottom: 1rem;
}

@media only screen and (max-width: 925px) {
  .card {
    width: 100%;
  }
}
</style>
