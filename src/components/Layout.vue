<template>
  <div id="grid">
    <server-list />
    <server-name />
    <channel-list />
    <user-info />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import ServerList from './ServerList.vue'
import ServerName from './ServerName.vue'
import ChannelList from './ChannelList.vue'
import UserInfo from './UserInfo.vue'

@Component({
  components: {
    ServerList,
    ServerName,
    ChannelList,
    UserInfo
  }
})
export default class Layout extends Vue {}
</script>

<style scoped>
#grid {
  display: grid;
  height: 100vh;
  grid-template-columns: 71px 240px auto 240px;
  grid-template-rows: 46px auto 52px;
  grid-template-areas: 
    'serverList serverName channelInfo channelInfo'
    'serverList channelList channelData userList'
    'serverList userInfo channelData userList'
  ;
}
</style>
