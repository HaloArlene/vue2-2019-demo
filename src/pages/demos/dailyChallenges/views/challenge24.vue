<template>
  <div class="view-challenge">
    <div class="penrose">
      <span />
      <span />
      <span />
    </div>
  </div>
</template>

<style lang="less" scoped>
.view-challenge {
  background-color: black;
  overflow: hidden;
}

.penrose {
  width: 20em;
  height: 20em;
  position: relative;
  color: red;
  top: -1em;
  left: -3em;
  animation: rotating 10s linear infinite;
  transform-origin: 66% 66%;
}

.penrose span {
  position: absolute;
  width: 100%;
  height: 100%;
  background-color: currentColor;
  clip-path: polygon(57% 0, 75% 0, 26% 85%, 89.5% 85%, 98.4% 100%, 0 100%);
}

.penrose span:nth-child(1) {
  transform: rotate(0deg);
  filter: brightness(1);
}

.penrose span:nth-child(2) {
  transform: rotate(120deg);
  filter: brightness(0.66);
  top: 18.3%;
  left: 43.3%;
}

.penrose span:nth-child(3) {
  transform: rotate(240deg);
  filter: brightness(0.33);
  top: 46.5%;
  left: 5.9%;
}

@keyframes rotating {
  to {
    transform: rotate(2turn);
    filter: hue-rotate(360deg);
  }
}
</style>