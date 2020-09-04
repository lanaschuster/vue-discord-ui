<template>
  <div id="grid">
    <server-list />
    <server-name />
    <channel-list />
    <user-info />
    <channel-info channelName="geral" description="Canal aberto para conversas" />
    <channel-data />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import ServerList from './ServerList.vue'
import ServerName from './ServerName.vue'
import ChannelList from './ChannelList.vue'
import UserInfo from './UserInfo.vue'
import ChannelInfo from './ChannelInfo.vue'
import ChannelData from './ChannelData.vue'

@Component({
  components: {
    ServerList,
    ServerName,
    ChannelList,
    UserInfo,
    ChannelInfo,
    ChannelData
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
