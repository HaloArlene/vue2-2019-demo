<template>
  <div class="view-challenge">
    <div>
      <h1>Who Am I</h1>
      <p>
        <span class="question">Who gives you milk?</span>
        <span class="answer">cow</span>
      </p>
      <p>
        <span class="question">Who likes to eat flies?</span>
        <span class="answer">frog</span>
      </p>
      <p>
        <span class="question">Who have large claws?</span>
        <span class="answer">crab</span>
      </p>
    </div>
  </div>
</template>

<style lang="less" scoped>
  .view-challenge {
    background: darkcyan;
  }

  h1 {
    font-family: sans-serif;
    color: gold;
    text-align: center;
    position: relative;

    &:after {
      content: '?';
      position: absolute;
      top: -0.5em;
      left: 0;
      font-size: 24em;
      transform: rotate(15deg);
      color: cyan;
      filter: opacity(0.3);
      text-shadow: 10px 10px 10px rgba(0, 0, 0, 0.2);
    }
  }

  p {
    width: 400px;
    height: 2.5em;
    color: gold;
    font-size: 24px;
    border: 2px solid gold;
    line-height: 2.5em;
    text-align: center;
    border-radius: 10px;
    font-family: sans-serif;
    letter-spacing: 2px;
    word-spacing: 2px;
    box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.2);
    position: relative;
    overflow: hidden;

    span {
      position: absolute;
      width: 100%;
      top: 0;
      left: 0;
      transition: 0.5s ease-out;
    }

    .question {
      left: 0;
    }

    &:hover {
      .question {
        left: 100%;
      }

      .answer {
        left: 0;
      }
    }

    .answer {
      color: whitesmoke;
      font-size: 1.1em;
      text-transform: uppercase;
      background: rgba(0, 0, 0, 0.1);
      left: -100%;
    }
  }
</style>
