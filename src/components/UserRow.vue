<template>
  <div class="user-row">
    <div class="avatar" :class="{ 'bot-avatar': isBot }"></div>
    <strong>{{ username }}</strong>
    <div v-if="isBot" class="bot">BOT</div>
  </div>
</template>
<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator'

@Component
export default class UserRow extends Vue {
  @Prop({
    type: String,
    required: true
  })
  private readonly username!: string

  @Prop({
    type: Boolean,
    required: false
  })
  private readonly isBot!: boolean
}
</script>
<style scoped lang="scss">
.user-row {
  display: flex;
  margin-top: 5px;
  padding: 5px;
  align-items: center;
  cursor: pointer;
  border-radius: 5px;
  background-color: transparent;
  transition: 0.2s;

  &:hover {
    background: rgba(255, 255, 255, 0.1);
  }

  strong {
    margin-left: 13px;
    font-weight: 500;
    color: var(--white);
    opacity: 0.7;
    white-space: nowrap;
    text-overflow: ellipsis;
    overflow: hidden;
  }

  .avatar {
    width: 32px;
    height: 32px;
    border-radius: 50%;
    flex-shrink: 0;
    background-color: var(--primary);

  }

  .bot-avatar {
    background-color: var(--mention-detail);
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
}
</style>