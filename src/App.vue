<template>
  <router-view/>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400;1,700&display=swap');
/* font-family: 'Space Mono', monospace; */

*, *::before, *::after {
  box-sizing: border-box;
}
* {
  margin: 0;
}
html, body {
  height: 100%;
}
body {
  line-height: 1.5;
  -webkit-font-smoothing: antialiased;
}
img, picture, video, canvas, svg {
  display: block;
  max-width: 100%;
}
input, button, textarea, select {
  font: inherit;
}
p, h1, h2, h3, h4, h5, h6 {
  overflow-wrap: break-word;
}
#root, #__next {
  isolation: isolate;
}
:root{
  /* primary */
  --scyan: hsl(172, 67%, 45%);

  /* neutral */
  --vdcyan: hsl(183, 100%, 15%);
  --dgcyan: hsl(186, 14%, 43%);
  --gcyan: hsl(184, 14%, 56%);
  --lgcyan: hsl(185, 41%, 84%);
  --vlgcyan: hsl(189, 41%, 97%);
  --white: hsl(0, 0%, 100%);
}
</style>
