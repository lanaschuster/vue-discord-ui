<template>
  <div class="channel-message" :class="{ 'has-mention': hasMentions}">
    <div class="avatar" :class="{ 'bot-avatar': isBot }"></div>
    <div class="message">
      <div class="user">
        <strong>{{ author }}</strong>
        <span v-if="isBot" class="bot">Bot</span>
        <span class="date">{{ date }}</span>
      </div>
      <div class="body">
        <slot />
      </div>
    </div>
  </div>
</template>
<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator'

@Component
export default class ChannelMessage extends Vue {
  @Prop({
    type: String,
    required: true
  })
  private readonly author!: string

  @Prop({
    type: String,
    required: true
  })
  private readonly date!: string

  @Prop({
    type: Boolean,
    required: false
  })
  private readonly hasMentions!: boolean

  @Prop({
    type: Boolean,
    required: false
  })
  private readonly isBot!: boolean
}
</script>
<style scoped lang="scss">
.channel-message {
  display: flex;
  align-items: center;
  padding: 8px 16px;
  margin-right: 4px;
  background-color: transparent;
  margin-top: 13px;

  &.has-mention {
    background-color: var(--mention-message);
    border-left: solid 2px var(--mention-detail);
  }

  &:hover {
    background-color: var(--quaternary);
  }
}

.avatar {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background-color: var(--secondary);
  flex-shrink: 0;

  &.bot-avatar {
    background-color: var(--mention-detail);
  }
}

.message {
  margin-left: 17px;
  height: 40px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;

  strong {
    color: var(--white);
    font-size: 16px;
  }

  .date {
    margin-left: 6px;
    color: var(--grey);
    font-size: 13px;
  }

  .bot {
    margin-left: 9px;
    background-color: var(--discord);
    color: var(--white);
    padding: 4px 5px;
    border-radius: 4px;
    text-transform: uppercase;
    font-size: 11px;
    font-weight: bold;
  }

  .body {
    color: var(--white);
    text-align: left;
    font-size: 16px;

    .mention {
      color: var(--link);
      cursor: pointer;

      &:hover {
        text-decoration: underline;
      }
    }
  }
}
</style>