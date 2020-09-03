<template>
  <div class="server-button"
    :class="{'has-notification': hasNotification, 'home': isHome}">
    <img v-if="isHome" class="image" src="../assets/images/logo.png">
    <div v-if="mentions" class="mentions">{{ mentions }}</div>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator';

@Component
export default class ServerButton extends Vue {
  @Prop({
    type: Boolean,
    required: false
  })
  private readonly selected!: boolean

  @Prop({
    type: Boolean,
    required: false
  })
  private readonly isHome!: boolean

  @Prop({
    type: Number,
    required: false
  })
  private readonly mentions!: number

  @Prop({
    type: Boolean,
    required: false
  })
  private readonly hasNotification!: boolean
}
</script>

<style scoped lang="scss">
.server-button {
  display: flex;
  flex-shrink: 0;
  align-items: center;
  justify-content: center;
  width: 48px;
  height: 48px;
  margin-bottom: 8px;
  background-color: var(--primary);
  cursor: pointer;
  position: relative;
  border-radius: 50%;
  transition: 0.2s;

  &.active, &:hover {
    border-radius: 16px;
    background-color: var(--discord);
  }
  
  .mentions {
    background-color: var(--notification);
    width: auto;
    height: 24px;
    padding: 0 4px;
    position: absolute;
    border-radius: 12px;
    bottom: -4px;
    right: -4px;
    text-align: right;
    font-size: 13px;
    font-weight: bold;
    color: var(--white);
    border: solid 4px var(--quaternary);
  }
}

.has-notification {
  &::before {
    content: '';
    width: 9px;
    height: 9px;
    background-color: var(--white);
    position: absolute;
    left: -17px;
    top: calc(50% - 4.5px);
    border-radius: 50%;
    display: block;
  }
}

.home {
  background-color: var(--rocketseat);
  &.active, &:hover {
    border-radius: 16px;
    background-color: var(--rocketseat);
  }
}

.image {
  width: 24px;
  height: 24px;
}
</style>
