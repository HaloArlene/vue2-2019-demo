<template>
  <div class="view-challenge">
    <div class="panda" />
  </div>
</template>

<style lang="less" scoped>
.view-challenge {
  background-color: mediumturquoise;
}

.panda {
  width: 21em;
  height: 16em;
  background-color: white;
  border: 0.5em solid #333;
  border-top-left-radius: 11em;
  border-top-right-radius: 11em;
  border-bottom-left-radius: 11em 6em;
  border-bottom-right-radius: 11em 6em;
  position: relative;
  background-image: radial-gradient(
      ellipse at 50% 60%,
      #333 1.2em,
      transparent 1em
    ),
    radial-gradient(ellipse at 50% 80%, #555 0.6em, transparent 0.6em);
  border-bottom-width: 1em;
  box-shadow: inset 1em -1em 0 #eee;
}

.panda::before,
.panda::after {
  content: "";
  position: absolute;
  width: 7em;
  height: 4em;
  top: 5.5em;
  display: block;
}

.panda::before {
  background-color: #333;
  border-radius: 50% 50% 45% 42%;
  left: 2.1em;
  transform: rotate(-45deg);
  box-shadow: 1em -7.2em 0 -0.4em #333;
  background-image: radial-gradient(
      circle at 5.1em 2em,
      white 0.3em,
      transparent 0.3em
    ),
    radial-gradient(circle at 4.6em 2em, #333 0.7em, transparent 0.7em),
    radial-gradient(circle at 4.5em 2em, white 1em, transparent 1em);
  animation: before-animate 1s ease-in-out infinite alternate;
}

.panda::after {
  left: 11em;
  background-color: #333;
  box-shadow: -1em -7.2em 0 -0.4em #333;
  background-image: radial-gradient(
      circle at 2.4em 1.5em,
      white 0.3em,
      transparent 0.3em
    ),
    radial-gradient(circle at 2.4em 2em, #333 0.7em, transparent 0.7em),
    radial-gradient(circle at 2.5em 2em, white 1em, transparent 1em);
  border-radius: 50% 50% 42% 45%;
  transform: rotate(45deg);
  animation: after-animate 1s ease-in-out infinite alternate -1s;
}

@keyframes before-animate {
  to {
    transform: rotate(-40deg);
    background-image: radial-gradient(
        circle at 4.9em 1.8em,
        white 0.3em,
        transparent 0.3em
      ),
      radial-gradient(circle at 4.4em 1.8em, #333 0.7em, transparent 0.7em),
      radial-gradient(circle at 4.5em 2em, white 1em, transparent 1em);
  }
}

@keyframes after-animate {
  to {
    transform: rotate(40deg);
    background-image: radial-gradient(
        circle at 2.6em 1.3em,
        white 0.3em,
        transparent 0.3em
      ),
      radial-gradient(circle at 2.6em 1.8em, #333 0.7em, transparent 0.7em),
      radial-gradient(circle at 2.5em 2em, white 1em, transparent 1em);
  }
}
</style>