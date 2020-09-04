<template>
  <div class="channel-list">
    <div class="category">
      <div>Canais de Texto</div>
      <div class="category-icon">
        <add-category-icon :size="21" />
      </div>
    </div>
    <channel-button channelName="geral" selected />
    <channel-button channelName="turma do lolzinho" />
    <channel-button channelName="devs" />
    <channel-button channelName="agario" />
    <channel-button channelName="crystal gems" />
  </div>
</template>
<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import ChannelButton from './ChannelButton.vue'

@Component({
  components: {
    ChannelButton
  }
})
export default class ChannelList extends Vue {}
</script>
<style scoped lang="scss">
.channel-list {
  grid-area: channelList;
  display: flex;
  flex-direction: column;
  padding: 24px 10px 0 16px;
  background-color: var(--secondary);
}

.category {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 6px;
  color: var(--grey);
  font-size: 12px;
  font-weight: 500;
  text-transform: uppercase;
  .category-icon {
    color: var(--symbol);
    cursor: pointer;
  };
}
</style>
