<template>
  <div class="grid">
    <div class="item">
      <div class="item-content">
        <img src="https://placeimg.com/195/400/any?1" />
      </div>
    </div>
    <div class="item">
      <div class="item-content">
        <img src="https://placeimg.com/400/195/any?2" />
      </div>
    </div>
    <div class="item">
      <div class="item-content">
        <img src="https://placeimg.com/195/400/any?3" />
      </div>
    </div>
    <div class="item">
      <div class="item-content">
        <img src="https://placeimg.com/400/195/any?4" />
      </div>
    </div>
    <div class="item">
      <div class="item-content">
        <img src="https://placeimg.com/195/400/any?5" />
      </div>
    </div>
  </div>
</template>

<script>
import 'web-animations-js';
import Muuri from 'muuri';

export default {
  name: 'Grid',
  mounted() {
    var grid = new Muuri('.grid', {
      layoutDuration: 400,
      layoutEasing: 'ease',
      dragEnabled: true,
    });

    console.log(grid.toString());
  },
};
</script>

<style lang="scss" scoped>
.grid {
  position: relative;
  opacity: 1;
  transition: opacity 0.8s linear 1s;
}

.item {
  position: absolute;
  margin: 5px;
  z-index: 1;
  max-width: 200px;
}
.item.muuri-item-hidden {
  z-index: 0;
}
.item.muuri-item-releasing {
  z-index: 2;
}
.item.muuri-item-dragging {
  z-index: 3;
}
.item-content {
  position: relative;
  cursor: pointer;
}
.item-content > img {
  display: block;
  border-radius: 6px;
}
</style>
