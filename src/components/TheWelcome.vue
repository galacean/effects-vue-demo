<script lang="ts">
import { Player } from '@galacean/effects';
import '@galacean/effects-plugin-model';

const json = '/assets/data.json';

export default {
  player: null,
  mounted() {
    const container = this.$refs.container;
    this.player = new Player({
      container,
      interactive: true,
    });

    this.player.loadScene(json);
  },
  beforeUnmount() {
    this.player?.dispose();
  },
}
</script>

<template>
  <div ref="container" style="width: 100vw; height: 100vh;"></div>
</template>
