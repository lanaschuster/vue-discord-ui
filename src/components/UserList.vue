<template>
  <div class="user-list">
    <div class="role">Disponível - 3</div>
    <user-row isBot username="DinnerBot"></user-row>
    <user-row username="Lana Schuster"></user-row>
    <user-row username="Luiz Carlos"></user-row>
    <div class="role">Offline - 4</div>
    <user-row username="Adrian"></user-row>
    <user-row username="Alisson"></user-row>
    <user-row username="Mauricio"></user-row>
    <user-row username="Natan"></user-row>
  </div>
</template>
<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import UserRow from './UserRow.vue'

@Component({
  components: {
    UserRow
  }
})
export default class UserList extends Vue {}
</script>
<style scoped lang="scss">
.user-list {
  grid-area: userList;
  display: flex;
  flex-direction: column;
  padding: 3px 6px 10px 16px;
  background-color: var(--secondary);
  max-height: calc(100vh - 46px);
  overflow-y: scroll;

  &::-webkit-scrollbar{
    width: 4px;
  }

  &::-webkit-scrollbar-thumb {
    background-color: var(--tertiary);
    border-radius: 4px;
  }

  &::-webkit-scrollbar-track {
    background-color: var(--secondary);
  }
}

.role {
  margin-top: 20px;
  color: var(--grey);
  font-weight: 500;
  font-size: 12px;
  text-transform: uppercase;
}

</style>