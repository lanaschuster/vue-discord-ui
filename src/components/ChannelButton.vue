<template>
  <div class="channel-button" :class="{ active: selected }">
    <div class="channel-info">
      <hashtag-icon class="hash-icon" :size="20" />
      <div>{{ channelName }}</div>
    </div>
    <div class="channel-actions">
      <invite-icon class="icon-actions" :size="16" />
      <settings-icon class="icon-actions" :size="16" />
    </div>
  </div>
</template>
<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator'

@Component
export default class ChannelButton extends Vue {
  @Prop({
    type: String,
    required: true
  })
  private readonly channelName!: string

  @Prop({
    type: Boolean,
    required: false
  })
  private readonly selected!: boolean
}
</script>
<style scoped lang="scss">
.channel-button {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  cursor: pointer;
  padding: 5px 3px;
  border-radius: 5px;
  background-color: transparent;

  div {
    display: flex;
    align-items: center;
  }

  .channel-info {
    div {
      color: var(--senary);
      margin-left: 5px;
    }
    .hash-icon {
      color: var(--symbol);
    }
  }

  .channel-actions {
    display: none;
    .icon-actions {
      color: var(--symbol);
      margin-left: 4px;
      transition: 0.2s;
      &:hover {
        color: var(--white);
      }
    }
  }

  &:hover, &.active {
    background-color: var(--quinary);
    .channel-info {
      div {
        color: var(--white);
      }
    }
    .channel-actions {
      display: flex;
    }
  }
}
</style>
