<template>
  <div class="quotes">
    <div class="quote">This was amazing<br />-Seth Raphael</div>
    <div class="quote">
      mind-reading spam calls<br />
      "Really Funny”<br />
      Mac King
    </div>
    <div class="quote">
      Unique and uncomplicated<br />

      Lee Earle
    </div>
    <div class="quote">
      "I agree that that's impressive" <br />
      James Randi
    </div>
    <div class="quote">
      "Seth Raphael blows the mind”<br />
      Teller
    </div>
    <div class="quote" style="display:none">
      "Oh come on!"<br />
      Penn
    </div>
    <div class="quote">
      Amaze<br />
      "one of the best tricks I've ever seen” <br />
      Andy (from thejerx.com)
    </div>
    <div class="quote">
      Fools the living crap out of me. It’s a good thing
      <br />
      Curtis Cam
    </div>

    <div class="quote">
      A fucking good magic trick<br />
      "OMG What Just Happened”<br />
      Robert Ramirez
    </div>

    <div class="quote">
      "Impressive techno-magic!"<br />
      Jeff McBride
    </div>
    <div class="quote">
      GET OUT OF MY HEADDD!<br />
      Sasha Fox
    </div>
  </div>
</template>

<style scoped>
.quote {
  padding-top: 4vh;
  text-align: center;
  /* background-color: red; */
  top: 0px;
  opacity: 0.03;
  transition: 1.2s;
  transition-timing-function: ease-in-out;
  font-family: "reenie_beanieregular";
  width: 20vw;
  height: 10vh;
  font-size: 2em;
  color: #fff;
}
.quote:hover {
  opacity: 1;
}

.quotes {
  font-size: 0.8em;
  grid-area: main;
  /* position: relative; */
  display: flex; /* or inline-flex */
  flex-flow: row wrap;
  justify-content: space-around;
  width: 100vw;
  overflow: hidden;
}
</style>
