<template>
  <div class="container">
    <div class="icon">
      <hashtag-icon :size="24" />
    </div>
    <h1 class="title">{{ channelName }}</h1>
    <div class="separator"></div>
    <div class="description">{{ description }}</div>
  </div>
</template>
<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator'

@Component
export default class ChannelInfo extends Vue {
  @Prop({
    type: String,
    required: true
  })
  private readonly channelName!: string

  @Prop({
    type: String,
    required: true
  })
  private readonly description!: string
}
</script>
<style scoped lang="scss">
.container {
  grid-area: channelInfo;
  background-color: var(--primary);
  display: flex;
  align-items: center;
  padding: 0 17px;
  z-index: 2;
  box-shadow: rgba(0, 0, 0, .9) 0 1px 0 0;
}

.title {
  color: var(--white);
  font-size: 16px;
  margin-left: 9px;
  font-weight: bold;
}

.description {
  color: var(--grey);
  font-size: 15px;
}

.separator {
  background-color: var(--white);
  height: 24px;
  width: 1px;
  opacity: .2;
  margin: 0 13px;
}

.icon {
  color: var(--symbol);
}
</style>