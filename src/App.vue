<template>
  <div id="app">
    <main>
      <h1>Villagers</h1>
      <svg
        class="waves"
        xmlns="http://www.w3.org/2000/svg"
        xmlns:xlink="http://www.w3.org/1999/xlink"
        viewBox="0 24 150 28"
        preserveAspectRatio="none"
        shape-rendering="auto"
      >
        <defs>
          <path
            id="gentle-wave"
            d="M-160 44c30 0 58-18 88-18s 58 18 88 18 58-18 88-18 58 18 88 18 v44h-352z"
          />
        </defs>
        <g class="parallax">
          <use xlink:href="#gentle-wave" x="48" y="0" fill="rgba(255,255,255,0.6)" />
          <use xlink:href="#gentle-wave" x="48" y="3" fill="rgba(255,255,255,0.4)" />
          <use xlink:href="#gentle-wave" x="48" y="5" fill="rgba(255,255,255,0.2)" />
          <use xlink:href="#gentle-wave" x="48" y="7" fill="#fff" />
        </g>
      </svg>

      <Search />
      <VillagerCard v-bind:villagers="villagers" />
    </main>
  </div>
</template>

<script>
import Search from "./components/Search";
import VillagerCard from "./components/VillagerCard";
import { VillagerList } from "./components/VillagerList";

export default {
  name: "app",
  components: {
    VillagerCard,
    Search
  },
  data() {
    return {
      villagers: VillagerList,
      search: ""
    };
  }
};
</script>

<style>
a,
abbr,
acronym,
address,
applet,
article,
aside,
audio,
b,
big,
blockquote,
body,
canvas,
caption,
center,
cite,
code,
dd,
del,
details,
dfn,
div,
dl,
dt,
em,
embed,
fieldset,
figcaption,
figure,
footer,
form,
h1,
h2,
h3,
h4,
h5,
h6,
header,
hgroup,
html,
i,
iframe,
img,
ins,
kbd,
label,
legend,
li,
mark,
menu,
nav,
object,
ol,
output,
p,
pre,
q,
ruby,
s,
samp,
section,
small,
span,
strike,
strong,
sub,
summary,
sup,
table,
tbody,
td,
tfoot,
th,
thead,
time,
tr,
tt,
u,
ul,
var,
video {
  margin: 0;
  padding: 0;
  border: 0;
  font-size: 100%;
  font: inherit;
  vertical-align: baseline;
}
article,
aside,
details,
figcaption,
figure,
footer,
header,
hgroup,
menu,
nav,
section {
  display: block;
}
body {
  line-height: 1;
}
ol,
ul {
  list-style: none;
}
blockquote,
q {
  quotes: none;
}
blockquote:after,
blockquote:before,
q:after,
q:before {
  content: "";
  content: none;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
}
input[type="search"]::-webkit-search-cancel-button,
input[type="search"]::-webkit-search-decoration,
input[type="search"]::-webkit-search-results-button,
input[type="search"]::-webkit-search-results-decoration {
  -webkit-appearance: none;
  -moz-appearance: none;
}
input[type="search"] {
  -webkit-appearance: none;
  -moz-appearance: none;
  -webkit-box-sizing: content-box;
  -moz-box-sizing: content-box;
  box-sizing: content-box;
}
textarea {
  overflow: auto;
  vertical-align: top;
  resize: vertical;
}
audio,
canvas,
video {
  display: inline-block;
  max-width: 100%;
}
audio:not([controls]) {
  display: none;
  height: 0;
}
[hidden] {
  display: none;
}
html {
  font-size: 100%;
  -webkit-text-size-adjust: 100%;
  -ms-text-size-adjust: 100%;
}
a:focus {
  outline: thin dotted;
}
a:active,
a:hover {
  outline: 0;
}
img {
  border: 0;
  -ms-interpolation-mode: bicubic;
}
figure {
  margin: 0;
}
form {
  margin: 0;
}
fieldset {
  border: 1px solid silver;
  margin: 0 2px;
  padding: 0.35em 0.625em 0.75em;
}
legend {
  border: 0;
  padding: 0;
  white-space: normal;
}
button,
input,
select,
textarea {
  font-size: 100%;
  margin: 0;
  vertical-align: baseline;
}
button,
input {
  line-height: normal;
}
button,
select {
  text-transform: none;
}
button,
html input[type="button"],
input[type="reset"],
input[type="submit"] {
  -webkit-appearance: button;
  cursor: pointer;
}
button[disabled],
html input[disabled] {
  cursor: default;
}
input[type="checkbox"],
input[type="radio"] {
  box-sizing: border-box;
  padding: 0;
}
input[type="search"] {
  -webkit-appearance: textfield;
  -moz-box-sizing: content-box;
  -webkit-box-sizing: content-box;
  box-sizing: content-box;
}
input[type="search"]::-webkit-search-cancel-button,
input[type="search"]::-webkit-search-decoration {
  -webkit-appearance: none;
}
button::-moz-focus-inner,
input::-moz-focus-inner {
  border: 0;
  padding: 0;
}
textarea {
  overflow: auto;
  vertical-align: top;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
}
button,
html,
input,
select,
textarea {
  color: #222;
}
::-moz-selection {
  background: #b3d4fc;
  text-shadow: none;
}
::selection {
  background: #b3d4fc;
  text-shadow: none;
}
img {
  vertical-align: middle;
}
fieldset {
  border: 0;
  margin: 0;
  padding: 0;
}
textarea {
  resize: vertical;
}
.chromeframe {
  margin: 0.2em 0;
  background: #ccc;
  color: #000;
  padding: 0.2em 0;
}

html {
  font-size: 62.5%;
}

@import url("https://fonts.googleapis.com/css2?family=Varela+Round&display=swap");
body {
  background-image: url("./assets/bg.png");
  background-repeat: repeat;
  font-family: "Varela Round", sans-serif;
}

h1 {
  font-size: 7rem;
  letter-spacing: 5px;
  text-align: center;
  text-transform: uppercase;
  color: rgb(66, 66, 66);
}

main {
  margin-bottom: 10px;
  width: 100%;
  max-width: 1200px;
  box-sizing: border-box;
  margin: 16px auto;
  border-radius: 40px;
  padding: 16px 0px;
  padding-bottom: 16px;
  background: #f5f8ff;
  color: #686868;
  overflow: hidden;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.06), 0 1px 2px rgba(0, 0, 0, 0.08);
}

.waves {
  position: relative;
  width: 100%;
  margin-bottom: -7px;
  max-height: 150px;
}
</style>
