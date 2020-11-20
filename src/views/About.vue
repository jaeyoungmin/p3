<template>
  <section class="kanban-demo">
    <h2 class="section-title"><span>Kanban Demo</span></h2>
    <div class="board muuri" style="height: 445px; boader:1px solid red;">
      <div
        class="board-column todo muuri-item muuri-item-shown"
        style="left: 0px; top: 0px; transform: translateX(0px) translateY(0px); display: block; touch-action: none; user-select: none; -webkit-user-drag: none; -webkit-tap-highlight-color: rgba(0, 0, 0, 0);"
      >
        <div
          class="board-column-header"
          style="opacity: 1; transform: scale(1);"
        >
          To do
        </div>
        <div
          class="board-column-content muuri todo"
          style="height: 395px;"
        ></div>
      </div>
      <div
        class="board-column working muuri-item muuri-item-shown"
        style="left: 0px; top: 0px; transform: translateX(307px) translateY(0px); display: block; touch-action: none; user-select: none; -webkit-user-drag: none; -webkit-tap-highlight-color: rgba(0, 0, 0, 0);"
      >
        <div
          class="board-column-header"
          style="opacity: 1; transform: scale(1);"
        >
          Working
        </div>
        <div
          class="board-column-content muuri working"
          style="height: 395px;"
        ></div>
      </div>
      <div
        class="board-column done muuri-item muuri-item-shown"
        style="left: 0px; top: 0px; transform: translateX(614px) translateY(0px); display: block; touch-action: none; user-select: none; -webkit-user-drag: none; -webkit-tap-highlight-color: rgba(0, 0, 0, 0);"
      >
        <div
          class="board-column-header"
          style="opacity: 1; transform: scale(1);"
        >
          Done
        </div>
        <div
          class="board-column-content muuri donw"
          style="height: 395px;"
        ></div>
      </div>
    </div>
  </section>
</template>

<script>
import 'web-animations-js';
import Muuri from 'muuri';

export default {
  mounted() {
    var grid = new Muuri('.board', { dragEnabled: true });

    console.log(grid.toString());
  },
};
</script>
<style lang="scss" scoped>
.board {
  position: relative;
  margin-left: 1%;
}
.board-column {
  position: absolute;
  left: 0;
  right: 0;
  width: 30%;
  margin: 0 1.5%;
  background: #f0f0f0;
  border-radius: 3px;
  z-index: 1;
}
.board-column.muuri-item-releasing {
  z-index: 2;
}
.board-column.muuri-item-dragging {
  z-index: 3;
  cursor: move;
}
.board-column-header {
  position: relative;
  height: 50px;
  line-height: 50px;
  overflow: hidden;
  padding: 0 20px;
  text-align: center;
  background: #333;
  color: #fff;
  border-radius: 3px 3px 0 0;
}
@media (max-width: 600px) {
  .board-column-header {
    text-indent: -1000px;
  }
}
.board-column.todo .board-column-header {
  background: #4a9ff9;
}
.board-column.working .board-column-header {
  background: #f9944a;
}
.board-column.done .board-column-header {
  background: #2ac06d;
}
.board-column-content {
  position: relative;
  border: 10px solid transparent;
  min-height: 95px;
}
.board-item {
  position: absolute;
  width: 100%;
  margin: 5px 0;
}
.board-item.muuri-item-releasing {
  z-index: 9998;
}
.board-item.muuri-item-dragging {
  z-index: 9999;
  cursor: move;
}
.board-item.muuri-item-hidden {
  z-index: 0;
}
.board-item-content {
  position: relative;
  padding: 20px;
  background: #fff;
  border-radius: 4px;
  font-size: 17px;
  cursor: pointer;
  -webkit-box-shadow: 0px 1px 3px 0 rgba(0, 0, 0, 0.2);
  box-shadow: 0px 1px 3px 0 rgba(0, 0, 0, 0.2);
}
@media (max-width: 600px) {
  .board-item-content {
    text-align: center;
  }
  .board-item-content span {
    display: none;
  }
}
</style>
