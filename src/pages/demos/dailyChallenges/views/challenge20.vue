<template>
  <div class="view-challenge">
    <div class="sea">
      <p class="title">the sea</p>
      <span class="wave"/>
      <span class="wave"/>
      <span class="wave"/>
    </div>
  </div>
</template>

<style lang="less" scoped>
  .view-challenge {
    background: linear-gradient(antiquewhite, navajowhite);
  }

  .sea {
    width: 300px;
    height: 300px;
    background-color: whitesmoke;
    background-image: linear-gradient(darkblue, rgba(255, 255, 255, 0) 80%, rgba(255, 255, 255, 0.5));
    border-radius: 5px;
    box-shadow: 0 2px 30px rgba(0, 0, 0, 0.2);
    position: relative;
    overflow: hidden;

    .title {
      color: white;
      font-size: 24px;
      font-family: serif;
      text-align: center;
      line-height: 250px;
      text-transform: uppercase;
      letter-spacing: 0.4em;
      position: absolute;
      z-index: 1;
      width: 100%;
    }

    .wave {
      position: absolute;
      top: -250px;
      left: -100px;
      width: 500px;
      height: 500px;
      background: deepskyblue;
      border-radius: 43%;
      filter: opacity(0.4);
      animation: drift linear infinite;
      transform-origin: 50% 48%;

      &:nth-of-type(1) {
        animation-duration: 5s;
      }

      &:nth-of-type(2) {
        animation-duration: 7s;
      }

      &:nth-of-type(3) {
        animation-duration: 9s;
        background-color: orangered;
        filter: opacity(0.1);
      }
    }
  }

  @keyframes drift {
    from {
      transform: rotate(360deg);
    }
  }
</style>
