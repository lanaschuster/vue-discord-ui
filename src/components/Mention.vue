<template>
  <span class="mention">{{ username }}</span>
</template>
<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator'

@Component
export default class ChannelMessage extends Vue {
  @Prop({
    type: String,
    required: true
  })
  private readonly username!: string
}
</script>
<style scoped lang="scss">
</style>