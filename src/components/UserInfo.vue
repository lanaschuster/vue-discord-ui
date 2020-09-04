<template>
  <div class="container">
    <div class="profile">
      <div class="avatar"></div>
      <div class="user-data">
        <strong>Lana Schuster</strong>
        <span>#0123</span>
      </div>
    </div>
    <div class="actions">
      <microphone-icon :size="20" />
      <headphone-icon :size="20" />
      <settings-icon :size="20" />
    </div>
  </div>
</template>
<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'

@Component
export default class UserInfo extends Vue {}
</script>
<style scoped lang="scss">
.container {
  grid-area: userInfo;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  padding: 10px;
  background-color: var(--quaternary);
  box-shadow: rgba(0, 0, 0, 0.2) 0 1px 0 0;
}

.profile {
  display: flex;
  align-items: center;
}

.avatar {
  width: 32px;
  height: 32px;
  border-radius: 50%;
  background-color: var(--grey);
}

.user-data {
  display: flex;
  flex-direction: column;
  margin-left: 8px;
  font-size: 13px;

  strong {
    display: block;
    color: var(--white)
  }

  span {
    color: var(--grey)
  }
}

.actions {
  color: var(--grey);
  span {
    cursor: pointer;
    transition: .2s;
    &:hover {
      color: var(--white);
    }
  }
}
</style>