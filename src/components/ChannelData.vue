<template>
  <div class="channel-data">
    <div class="messages">
      <channel-message author="Lana Schuster" date="04/09/2020 14:32">
        Oii, tudo bem?
      </channel-message>
      <channel-message author="Luiz Carlos" date="04/09/2020 14:33" hasMentions>
        Oi, tudo bem sim <mention username="Lana Schuster" /> e vc?
      </channel-message>
      <channel-message author="Lana Schuster" date="04/09/2020 14:33">
        Bem tbm
      </channel-message>
      <channel-message author="Luiz Carlos" date="04/09/2020 14:38">
        To com fome
      </channel-message>
      <channel-message author="Dinner Bot" date="04/09/2020 14:39" isBot>
        Tome aqui um spaguette
      </channel-message>
      <channel-message author="Lana Schuster" date="04/09/2020 14:41">
        Hmm, eu aceito rsrs
      </channel-message>
      <channel-message author="Luiz Carlos" date="04/09/2020 14:38">
        &#127837;
      </channel-message>
    </div>
    <div class="input-wrapper">
      <input type="text" placeholder="Conversar em #geral">
      <div class="icon">
        <at-icon :size="24" />
      </div>
    </div>
  </div>
</template>
<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import ChannelMessage from './ChannelMessage.vue'
import Mention from './Mention.vue'

@Component({
  components: {
    ChannelMessage,
    Mention
  }
})
export default class ChannelData extends Vue {}
</script>
<style scoped lang="scss">
.channel-data {
  grid-area: channelData;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  background-color: var(--primary);
  flex: 1;
}

.messages {
  display: flex;
  flex-direction: column;
  height: calc(100vh - 46px - 68px);
  max-height: calc(100vh - 46px - 68px);
  overflow-y: scroll;

  .channel-message:first-child {
    margin-top: 0;
  }

  &::-webkit-scrollbar{
    width: 8px;
  }

  &::-webkit-scrollbar-thumb {
    background-color: var(--tertiary);
    border-radius: 4px;
  }

  &::-webkit-scrollbar-track {
    background-color: var(--secondary);
  }
}

.input-wrapper {
  width: 100%;
  padding: 0 16px;
  height: 68px;

  input {
    width: 100%;
    height: 44px;
    padding: 0 10px 0 57px;
    border-radius: 5px;
    color: var(--white);
    background-color: var(--chat-input);
    position: relative;

    &::placeholder {
      color: var(--grey);
    }
  }

  .icon {
    color: var(--grey);
    position: relative;
    top: -50%;
    left: 14px;
    transition: 0.2s;
    width: 24px;
  }
}
</style>