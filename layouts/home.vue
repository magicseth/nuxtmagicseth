<template>
  <div>
    <div
      style="position: absolute; top: 0px; left: 0px; width: 50%;        height: 50%;        background-color: red;       "
    >
      okay
    </div>

    <div class="fullgrid">
      <div class="header">
        <menu-blob style="height: 100%" />
      </div>
      <quotes-bg />
      <Nuxt />

      <div class="footer">
        <div>Seth Raphael</div>
        <div class="footerLinks">
          <div>TED Fellow</div>
          <circle-blob width="2.5vh" height="2.5vh" />
          <div>
            <svg
              width="2.5vh"
              height="2.5vh"
              viewBox="0 0 56 57"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M54.8038 20.1563C52.8331 12.7815 48.5211 5.00612 40.736 1.78308C30.1413 -2.60536 19.566 2.32936 16.854 3.60401C9.82981 6.93631 6.16165 11.7982 5.20559 13.1275C4.5422 14.0561 -2.16976 23.9802 0.717945 35.361C4.52269 50.3291 20.8148 60.4534 36.9898 55.9011C53.438 51.276 58.6281 34.4688 54.8038 20.1563Z"
                fill="#5CBFB7"
              />
            </svg>
          </div>
          <div>Parent of 5</div>
          <div>
            <svg
              width="2.5vh"
              height="2.5vh"
              viewBox="0 0 56 57"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M54.8038 20.1563C52.8331 12.7815 48.5211 5.00612 40.736 1.78308C30.1413 -2.60536 19.566 2.32936 16.854 3.60401C9.82981 6.93631 6.16165 11.7982 5.20559 13.1275C4.5422 14.0561 -2.16976 23.9802 0.717945 35.361C4.52269 50.3291 20.8148 60.4534 36.9898 55.9011C53.438 51.276 58.6281 34.4688 54.8038 20.1563Z"
                fill="#5CBFB7"
              />
            </svg>
          </div>
          <div>Inventor at Google</div>
          <div>
            <svg
              width="2.5vh"
              height="2.5vh"
              viewBox="0 0 56 57"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M54.8038 20.1563C52.8331 12.7815 48.5211 5.00612 40.736 1.78308C30.1413 -2.60536 19.566 2.32936 16.854 3.60401C9.82981 6.93631 6.16165 11.7982 5.20559 13.1275C4.5422 14.0561 -2.16976 23.9802 0.717945 35.361C4.52269 50.3291 20.8148 60.4534 36.9898 55.9011C53.438 51.276 58.6281 34.4688 54.8038 20.1563Z"
                fill="#5CBFB7"
              />
            </svg>
          </div>
          <div>Degree in wonder from MIT</div>
        </div>
      </div>
    </div>
  </div>
</template>
<style scoped>
.fullgrid {
  display: grid;
  background-color: #333333;
  height: 100vh;

  grid-template-columns: auto;
  grid-template-rows: 10vh auto 15vh;
  grid-template-areas:
    "header "
    "main "
    "footer ";
}

.header {
  /* background-color: green; */
  grid-area: header;
  margin-left: -33vh;
  transition: 0.3s;
}

.header:hover {
  /* background-color: green; */
  margin-left: 0;
}

.main,
.impossiblecircle {
  grid-area: main;
  place-self: center;
  position: relative;
}
.main {
  min-width: 10vw;
  min-height: 10vw;
  /* opacity: 0; */
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
.impossiblecircle:hover .openblob {
  transform: scale(4);
}
.footer {
  grid-area: footer;
  font-family: "rift_softregular";
  font-size: min(4vw, 10vh);
  padding-left: 5vh;
  color: #7a7a7a;
  display: grid;

  grid-template-columns: max-content auto;
  grid-template-rows: auto;
  grid-template-areas: "footerSeth footerLinks ";
}

.footer div {
  align-self: center;
}
.footerLinks {
  align-self: center;

  display: flex;
  justify-content: space-evenly;
  font-size: 2vw;
}
.footerLinks svg {
  opacity: 0.3;
}
</style>
