<template>
  <div class="c-card">
    <div class="content">
      <div class="header">{{ header }}</div>
      <div class="body">
        <slot/>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'

@Component
export default class CCard extends Vue {
  @Prop() private header!: string;
}
</script>

<style scoped>
.c-card {
  width: 100%;
  padding: 4px 8px;
}
.content {
  background-color: #ffffff;
  border-radius: 5px;
  box-shadow: 0 0 2px rgba(0, 0, 0, 0.15);
  padding: 12px 8px;
}
</style>
