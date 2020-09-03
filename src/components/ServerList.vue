<template>
  <div class="container">
    <server-button isHome />
    <div class="separator"></div>
    <server-button :mentions="3" />
    <server-button />
    <server-button hasNotification />
    <server-button />
    <server-button />
    <server-button />
    <server-button />
    <server-button :mentions="42" hasNotification />
    <server-button />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import ServerButton from './ServerButton.vue'

@Component({
  components: {
    ServerButton
  }
})
export default class ServerList extends Vue {}
</script>

<style scoped lang="scss">
.container {
  grid-area: serverList;
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: var(--tertiary);
  padding: 11px 0;
  max-height: 100vh;
  overflow-y: scroll;
  &::-webkit-scrollbar {
    display: none;
  }
}

.separator {
  width: 32px;
  border-bottom: solid 2px var(--quaternary);
  margin-bottom: 8px;
}
</style>
