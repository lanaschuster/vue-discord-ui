<template>
  <div class="container">
    <div class="title">Server Name</div>
    <div class="icon">
      <expand-icon :size="28" />
    </div>
  </div>
</template>
<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'

@Component
export default class ServerName extends Vue {}
</script>
<style scoped>
.container {
  grid-area: serverName;
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: var(--secondary);
  padding: 0 11px 0 16px;
  box-shadow: rgba(0,0,0,0.9) 0 1px 0 0;
  z-index: 2; 
}

.title {
  color: var(--white);
  font-size: 16px;
  font-weight: bold;
}

.icon {
  color: var(--white);
  cursor: pointer;
}
</style>