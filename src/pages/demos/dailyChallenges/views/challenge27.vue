<template>
  <div class="view-challenge">
    <div class="court">
      <div class="left-paddle" />
      <div class="ball" />
      <div class="right-paddle" />
    </div>
  </div>
</template>

<style lang="less" scoped>
.view-challenge {
  background: linear-gradient(dimgray, black);
}

.court {
  width: 20em;
  height: 20em;
  color: white;
  border: 1em solid currentColor;
  font-size: 16px;
  position: relative;
}

.left-paddle,
.right-paddle {
  width: 1em;
  height: calc(50% - 1em);
  background-color: currentColor;
  position: absolute;
  animation: 1s linear infinite alternate;
}

.left-paddle {
  top: 1em;
  left: 1em;
  animation-name: left-moving;
}

.right-paddle {
  bottom: 1em;
  right: 1em;
  animation-name: right-moving;
}

.ball {
  width: 100%;
  height: 1em;
  border-left: 1em solid currentColor;
  position: absolute;
  left: 2em;
  top: calc(50% - 1.5em);
  animation: bounce 1s linear infinite alternate;
}

@keyframes left-moving {
  to {
    transform: translateY(100%);
  }
}

@keyframes right-moving {
  to {
    transform: translateY(-100%);
  }
}

@keyframes bounce {
  to {
    left: calc(100% - 3em);
  }
}
</style>