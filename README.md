# DATS-6103-Individual-Project-3
<b>

<p>
<center>
<font size="6">
Project 3: Airbnb Pricing Strategy
</font>
</center>
</p>

<p>
<center>
<font size="4">
By Gaofeng Huang
</font>
</center>
</p>

<p>
<center>
<font size="3">
Class: DATS6103 Data Mining (19Spring) of 15:30-18:00, Thursday.
</font>
</center>
</p>

<p>
<center>
<font size="3">
<a href="https://public.opendatasoft.com/explore/dataset/airbnb-listings/export/?disjunctive.host_verifications&disjunctive.amenities&disjunctive.features&location=15,51.5198,-0.16183&basemap=jawg.streets&dataChart=eyJxdWVyaWVzIjpbeyJjaGFydHMiOlt7InR5cGUiOiJjb2x1bW4iLCJmdW5jIjoiQ09VTlQiLCJ5QXhpcyI6Imhvc3RfbGlzdGluZ3NfY291bnQiLCJzY2llbnRpZmljRGlzcGxheSI6dHJ1ZSwiY29sb3IiOiJyYW5nZS1jdXN0b20ifV0sInhBeGlzIjoiY2l0eSIsIm1heHBvaW50cyI6IiIsInRpbWVzY2FsZSI6IiIsInNvcnQiOiIiLCJzZXJpZXNCcmVha2Rvd24iOiJyb29tX3R5cGUiLCJjb25maWciOnsiZGF0YXNldCI6ImFpcmJuYi1saXN0aW5ncyIsIm9wdGlvbnMiOnsiZGlzanVuY3RpdmUuaG9zdF92ZXJpZmljYXRpb25zIjp0cnVlLCJkaXNqdW5jdGl2ZS5hbWVuaXRpZXMiOnRydWUsImRpc2p1bmN0aXZlLmZlYXR1cmVzIjp0cnVlfX19XSwidGltZXNjYWxlIjoiIiwiZGlzcGxheUxlZ2VuZCI6dHJ1ZSwiYWxpZ25Nb250aCI6dHJ1ZX0%3D">
    Source 1: Airbnb Listings 
    </a><br>
<a href="https://data.worldbank.org/indicator/ST.INT.ARVL">
    Source 2: World Bank Tourists Arrivals 
    </a><br>
<a href="https://github.com/lucasmonteiro001/free-world-hotel-database/blob/master/hotels.csv.zip">
    Source 3: Hotels Data From GitHub 
    </a><br>
</font>
</center>
</p>

</b>

<!DOCTYPE html>
<html>
<head><meta charset="utf-8" />

<title>Airbnb</title>

<script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.0.3/jquery.min.js"></script>



<style type="text/css">
    /*!
*
* Twitter Bootstrap
*
*/
/*!
 * Bootstrap v3.3.7 (http://getbootstrap.com)
 * Copyright 2011-2016 Twitter, Inc.
 * Licensed under MIT (https://github.com/twbs/bootstrap/blob/master/LICENSE)
 */
/*! normalize.css v3.0.3 | MIT License | github.com/necolas/normalize.css */
html {
  font-family: sans-serif;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
}
body {
  margin: 0;
}
article,
aside,
details,
figcaption,
figure,
footer,
header,
hgroup,
main,
menu,
nav,
section,
summary {
  display: block;
}
audio,
canvas,
progress,
video {
  display: inline-block;
  vertical-align: baseline;
}
audio:not([controls]) {
  display: none;
  height: 0;
}
[hidden],
template {
  display: none;
}
a {
  background-color: transparent;
}
a:active,
a:hover {
  outline: 0;
}
abbr[title] {
  border-bottom: 1px dotted;
}
b,
strong {
  font-weight: bold;
}
dfn {
  font-style: italic;
}
h1 {
  font-size: 2em;
  margin: 0.67em 0;
}
mark {
  background: #ff0;
  color: #000;
}
small {
  font-size: 80%;
}
sub,
sup {
  font-size: 75%;
  line-height: 0;
  position: relative;
  vertical-align: baseline;
}
sup {
  top: -0.5em;
}
sub {
  bottom: -0.25em;
}
img {
  border: 0;
}
svg:not(:root) {
  overflow: hidden;
}
figure {
  margin: 1em 40px;
}
hr {
  box-sizing: content-box;
  height: 0;
}
pre {
  overflow: auto;
}
code,
kbd,
pre,
samp {
  font-family: monospace, monospace;
  font-size: 1em;
}
button,
input,
optgroup,
select,
textarea {
  color: inherit;
  font: inherit;
  margin: 0;
}
button {
  overflow: visible;
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
button::-moz-focus-inner,
input::-moz-focus-inner {
  border: 0;
  padding: 0;
}
input {
  line-height: normal;
}
input[type="checkbox"],
input[type="radio"] {
  box-sizing: border-box;
  padding: 0;
}
input[type="number"]::-webkit-inner-spin-button,
input[type="number"]::-webkit-outer-spin-button {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: textfield;
  box-sizing: content-box;
}
input[type="search"]::-webkit-search-cancel-button,
input[type="search"]::-webkit-search-decoration {
  -webkit-appearance: none;
}
fieldset {
  border: 1px solid #c0c0c0;
  margin: 0 2px;
  padding: 0.35em 0.625em 0.75em;
}
legend {
  border: 0;
  padding: 0;
}
textarea {
  overflow: auto;
}
optgroup {
  font-weight: bold;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
}
td,
th {
  padding: 0;
}
/*! Source: https://github.com/h5bp/html5-boilerplate/blob/master/src/css/main.css */
@media print {
  *,
  *:before,
  *:after {
    background: transparent !important;
    box-shadow: none !important;
    text-shadow: none !important;
  }
  a,
  a:visited {
    text-decoration: underline;
  }
  a[href]:after {
    content: " (" attr(href) ")";
  }
  abbr[title]:after {
    content: " (" attr(title) ")";
  }
  a[href^="#"]:after,
  a[href^="javascript:"]:after {
    content: "";
  }
  pre,
  blockquote {
    border: 1px solid #999;
    page-break-inside: avoid;
  }
  thead {
    display: table-header-group;
  }
  tr,
  img {
    page-break-inside: avoid;
  }
  img {
    max-width: 100% !important;
  }
  p,
  h2,
  h3 {
    orphans: 3;
    widows: 3;
  }
  h2,
  h3 {
    page-break-after: avoid;
  }
  .navbar {
    display: none;
  }
  .btn > .caret,
  .dropup > .btn > .caret {
    border-top-color: #000 !important;
  }
  .label {
    border: 1px solid #000;
  }
  .table {
    border-collapse: collapse !important;
  }
  .table td,
  .table th {
    background-color: #fff !important;
  }
  .table-bordered th,
  .table-bordered td {
    border: 1px solid #ddd !important;
  }
}
@font-face {
  font-family: 'Glyphicons Halflings';
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot');
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot?#iefix') format('embedded-opentype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff2') format('woff2'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff') format('woff'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.ttf') format('truetype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.svg#glyphicons_halflingsregular') format('svg');
}
.glyphicon {
  position: relative;
  top: 1px;
  display: inline-block;
  font-family: 'Glyphicons Halflings';
  font-style: normal;
  font-weight: normal;
  line-height: 1;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.glyphicon-asterisk:before {
  content: "\002a";
}
.glyphicon-plus:before {
  content: "\002b";
}
.glyphicon-euro:before,
.glyphicon-eur:before {
  content: "\20ac";
}
.glyphicon-minus:before {
  content: "\2212";
}
.glyphicon-cloud:before {
  content: "\2601";
}
.glyphicon-envelope:before {
  content: "\2709";
}
.glyphicon-pencil:before {
  content: "\270f";
}
.glyphicon-glass:before {
  content: "\e001";
}
.glyphicon-music:before {
  content: "\e002";
}
.glyphicon-search:before {
  content: "\e003";
}
.glyphicon-heart:before {
  content: "\e005";
}
.glyphicon-star:before {
  content: "\e006";
}
.glyphicon-star-empty:before {
  content: "\e007";
}
.glyphicon-user:before {
  content: "\e008";
}
.glyphicon-film:before {
  content: "\e009";
}
.glyphicon-th-large:before {
  content: "\e010";
}
.glyphicon-th:before {
  content: "\e011";
}
.glyphicon-th-list:before {
  content: "\e012";
}
.glyphicon-ok:before {
  content: "\e013";
}
.glyphicon-remove:before {
  content: "\e014";
}
.glyphicon-zoom-in:before {
  content: "\e015";
}
.glyphicon-zoom-out:before {
  content: "\e016";
}
.glyphicon-off:before {
  content: "\e017";
}
.glyphicon-signal:before {
  content: "\e018";
}
.glyphicon-cog:before {
  content: "\e019";
}
.glyphicon-trash:before {
  content: "\e020";
}
.glyphicon-home:before {
  content: "\e021";
}
.glyphicon-file:before {
  content: "\e022";
}
.glyphicon-time:before {
  content: "\e023";
}
.glyphicon-road:before {
  content: "\e024";
}
.glyphicon-download-alt:before {
  content: "\e025";
}
.glyphicon-download:before {
  content: "\e026";
}
.glyphicon-upload:before {
  content: "\e027";
}
.glyphicon-inbox:before {
  content: "\e028";
}
.glyphicon-play-circle:before {
  content: "\e029";
}
.glyphicon-repeat:before {
  content: "\e030";
}
.glyphicon-refresh:before {
  content: "\e031";
}
.glyphicon-list-alt:before {
  content: "\e032";
}
.glyphicon-lock:before {
  content: "\e033";
}
.glyphicon-flag:before {
  content: "\e034";
}
.glyphicon-headphones:before {
  content: "\e035";
}
.glyphicon-volume-off:before {
  content: "\e036";
}
.glyphicon-volume-down:before {
  content: "\e037";
}
.glyphicon-volume-up:before {
  content: "\e038";
}
.glyphicon-qrcode:before {
  content: "\e039";
}
.glyphicon-barcode:before {
  content: "\e040";
}
.glyphicon-tag:before {
  content: "\e041";
}
.glyphicon-tags:before {
  content: "\e042";
}
.glyphicon-book:before {
  content: "\e043";
}
.glyphicon-bookmark:before {
  content: "\e044";
}
.glyphicon-print:before {
  content: "\e045";
}
.glyphicon-camera:before {
  content: "\e046";
}
.glyphicon-font:before {
  content: "\e047";
}
.glyphicon-bold:before {
  content: "\e048";
}
.glyphicon-italic:before {
  content: "\e049";
}
.glyphicon-text-height:before {
  content: "\e050";
}
.glyphicon-text-width:before {
  content: "\e051";
}
.glyphicon-align-left:before {
  content: "\e052";
}
.glyphicon-align-center:before {
  content: "\e053";
}
.glyphicon-align-right:before {
  content: "\e054";
}
.glyphicon-align-justify:before {
  content: "\e055";
}
.glyphicon-list:before {
  content: "\e056";
}
.glyphicon-indent-left:before {
  content: "\e057";
}
.glyphicon-indent-right:before {
  content: "\e058";
}
.glyphicon-facetime-video:before {
  content: "\e059";
}
.glyphicon-picture:before {
  content: "\e060";
}
.glyphicon-map-marker:before {
  content: "\e062";
}
.glyphicon-adjust:before {
  content: "\e063";
}
.glyphicon-tint:before {
  content: "\e064";
}
.glyphicon-edit:before {
  content: "\e065";
}
.glyphicon-share:before {
  content: "\e066";
}
.glyphicon-check:before {
  content: "\e067";
}
.glyphicon-move:before {
  content: "\e068";
}
.glyphicon-step-backward:before {
  content: "\e069";
}
.glyphicon-fast-backward:before {
  content: "\e070";
}
.glyphicon-backward:before {
  content: "\e071";
}
.glyphicon-play:before {
  content: "\e072";
}
.glyphicon-pause:before {
  content: "\e073";
}
.glyphicon-stop:before {
  content: "\e074";
}
.glyphicon-forward:before {
  content: "\e075";
}
.glyphicon-fast-forward:before {
  content: "\e076";
}
.glyphicon-step-forward:before {
  content: "\e077";
}
.glyphicon-eject:before {
  content: "\e078";
}
.glyphicon-chevron-left:before {
  content: "\e079";
}
.glyphicon-chevron-right:before {
  content: "\e080";
}
.glyphicon-plus-sign:before {
  content: "\e081";
}
.glyphicon-minus-sign:before {
  content: "\e082";
}
.glyphicon-remove-sign:before {
  content: "\e083";
}
.glyphicon-ok-sign:before {
  content: "\e084";
}
.glyphicon-question-sign:before {
  content: "\e085";
}
.glyphicon-info-sign:before {
  content: "\e086";
}
.glyphicon-screenshot:before {
  content: "\e087";
}
.glyphicon-remove-circle:before {
  content: "\e088";
}
.glyphicon-ok-circle:before {
  content: "\e089";
}
.glyphicon-ban-circle:before {
  content: "\e090";
}
.glyphicon-arrow-left:before {
  content: "\e091";
}
.glyphicon-arrow-right:before {
  content: "\e092";
}
.glyphicon-arrow-up:before {
  content: "\e093";
}
.glyphicon-arrow-down:before {
  content: "\e094";
}
.glyphicon-share-alt:before {
  content: "\e095";
}
.glyphicon-resize-full:before {
  content: "\e096";
}
.glyphicon-resize-small:before {
  content: "\e097";
}
.glyphicon-exclamation-sign:before {
  content: "\e101";
}
.glyphicon-gift:before {
  content: "\e102";
}
.glyphicon-leaf:before {
  content: "\e103";
}
.glyphicon-fire:before {
  content: "\e104";
}
.glyphicon-eye-open:before {
  content: "\e105";
}
.glyphicon-eye-close:before {
  content: "\e106";
}
.glyphicon-warning-sign:before {
  content: "\e107";
}
.glyphicon-plane:before {
  content: "\e108";
}
.glyphicon-calendar:before {
  content: "\e109";
}
.glyphicon-random:before {
  content: "\e110";
}
.glyphicon-comment:before {
  content: "\e111";
}
.glyphicon-magnet:before {
  content: "\e112";
}
.glyphicon-chevron-up:before {
  content: "\e113";
}
.glyphicon-chevron-down:before {
  content: "\e114";
}
.glyphicon-retweet:before {
  content: "\e115";
}
.glyphicon-shopping-cart:before {
  content: "\e116";
}
.glyphicon-folder-close:before {
  content: "\e117";
}
.glyphicon-folder-open:before {
  content: "\e118";
}
.glyphicon-resize-vertical:before {
  content: "\e119";
}
.glyphicon-resize-horizontal:before {
  content: "\e120";
}
.glyphicon-hdd:before {
  content: "\e121";
}
.glyphicon-bullhorn:before {
  content: "\e122";
}
.glyphicon-bell:before {
  content: "\e123";
}
.glyphicon-certificate:before {
  content: "\e124";
}
.glyphicon-thumbs-up:before {
  content: "\e125";
}
.glyphicon-thumbs-down:before {
  content: "\e126";
}
.glyphicon-hand-right:before {
  content: "\e127";
}
.glyphicon-hand-left:before {
  content: "\e128";
}
.glyphicon-hand-up:before {
  content: "\e129";
}
.glyphicon-hand-down:before {
  content: "\e130";
}
.glyphicon-circle-arrow-right:before {
  content: "\e131";
}
.glyphicon-circle-arrow-left:before {
  content: "\e132";
}
.glyphicon-circle-arrow-up:before {
  content: "\e133";
}
.glyphicon-circle-arrow-down:before {
  content: "\e134";
}
.glyphicon-globe:before {
  content: "\e135";
}
.glyphicon-wrench:before {
  content: "\e136";
}
.glyphicon-tasks:before {
  content: "\e137";
}
.glyphicon-filter:before {
  content: "\e138";
}
.glyphicon-briefcase:before {
  content: "\e139";
}
.glyphicon-fullscreen:before {
  content: "\e140";
}
.glyphicon-dashboard:before {
  content: "\e141";
}
.glyphicon-paperclip:before {
  content: "\e142";
}
.glyphicon-heart-empty:before {
  content: "\e143";
}
.glyphicon-link:before {
  content: "\e144";
}
.glyphicon-phone:before {
  content: "\e145";
}
.glyphicon-pushpin:before {
  content: "\e146";
}
.glyphicon-usd:before {
  content: "\e148";
}
.glyphicon-gbp:before {
  content: "\e149";
}
.glyphicon-sort:before {
  content: "\e150";
}
.glyphicon-sort-by-alphabet:before {
  content: "\e151";
}
.glyphicon-sort-by-alphabet-alt:before {
  content: "\e152";
}
.glyphicon-sort-by-order:before {
  content: "\e153";
}
.glyphicon-sort-by-order-alt:before {
  content: "\e154";
}
.glyphicon-sort-by-attributes:before {
  content: "\e155";
}
.glyphicon-sort-by-attributes-alt:before {
  content: "\e156";
}
.glyphicon-unchecked:before {
  content: "\e157";
}
.glyphicon-expand:before {
  content: "\e158";
}
.glyphicon-collapse-down:before {
  content: "\e159";
}
.glyphicon-collapse-up:before {
  content: "\e160";
}
.glyphicon-log-in:before {
  content: "\e161";
}
.glyphicon-flash:before {
  content: "\e162";
}
.glyphicon-log-out:before {
  content: "\e163";
}
.glyphicon-new-window:before {
  content: "\e164";
}
.glyphicon-record:before {
  content: "\e165";
}
.glyphicon-save:before {
  content: "\e166";
}
.glyphicon-open:before {
  content: "\e167";
}
.glyphicon-saved:before {
  content: "\e168";
}
.glyphicon-import:before {
  content: "\e169";
}
.glyphicon-export:before {
  content: "\e170";
}
.glyphicon-send:before {
  content: "\e171";
}
.glyphicon-floppy-disk:before {
  content: "\e172";
}
.glyphicon-floppy-saved:before {
  content: "\e173";
}
.glyphicon-floppy-remove:before {
  content: "\e174";
}
.glyphicon-floppy-save:before {
  content: "\e175";
}
.glyphicon-floppy-open:before {
  content: "\e176";
}
.glyphicon-credit-card:before {
  content: "\e177";
}
.glyphicon-transfer:before {
  content: "\e178";
}
.glyphicon-cutlery:before {
  content: "\e179";
}
.glyphicon-header:before {
  content: "\e180";
}
.glyphicon-compressed:before {
  content: "\e181";
}
.glyphicon-earphone:before {
  content: "\e182";
}
.glyphicon-phone-alt:before {
  content: "\e183";
}
.glyphicon-tower:before {
  content: "\e184";
}
.glyphicon-stats:before {
  content: "\e185";
}
.glyphicon-sd-video:before {
  content: "\e186";
}
.glyphicon-hd-video:before {
  content: "\e187";
}
.glyphicon-subtitles:before {
  content: "\e188";
}
.glyphicon-sound-stereo:before {
  content: "\e189";
}
.glyphicon-sound-dolby:before {
  content: "\e190";
}
.glyphicon-sound-5-1:before {
  content: "\e191";
}
.glyphicon-sound-6-1:before {
  content: "\e192";
}
.glyphicon-sound-7-1:before {
  content: "\e193";
}
.glyphicon-copyright-mark:before {
  content: "\e194";
}
.glyphicon-registration-mark:before {
  content: "\e195";
}
.glyphicon-cloud-download:before {
  content: "\e197";
}
.glyphicon-cloud-upload:before {
  content: "\e198";
}
.glyphicon-tree-conifer:before {
  content: "\e199";
}
.glyphicon-tree-deciduous:before {
  content: "\e200";
}
.glyphicon-cd:before {
  content: "\e201";
}
.glyphicon-save-file:before {
  content: "\e202";
}
.glyphicon-open-file:before {
  content: "\e203";
}
.glyphicon-level-up:before {
  content: "\e204";
}
.glyphicon-copy:before {
  content: "\e205";
}
.glyphicon-paste:before {
  content: "\e206";
}
.glyphicon-alert:before {
  content: "\e209";
}
.glyphicon-equalizer:before {
  content: "\e210";
}
.glyphicon-king:before {
  content: "\e211";
}
.glyphicon-queen:before {
  content: "\e212";
}
.glyphicon-pawn:before {
  content: "\e213";
}
.glyphicon-bishop:before {
  content: "\e214";
}
.glyphicon-knight:before {
  content: "\e215";
}
.glyphicon-baby-formula:before {
  content: "\e216";
}
.glyphicon-tent:before {
  content: "\26fa";
}
.glyphicon-blackboard:before {
  content: "\e218";
}
.glyphicon-bed:before {
  content: "\e219";
}
.glyphicon-apple:before {
  content: "\f8ff";
}
.glyphicon-erase:before {
  content: "\e221";
}
.glyphicon-hourglass:before {
  content: "\231b";
}
.glyphicon-lamp:before {
  content: "\e223";
}
.glyphicon-duplicate:before {
  content: "\e224";
}
.glyphicon-piggy-bank:before {
  content: "\e225";
}
.glyphicon-scissors:before {
  content: "\e226";
}
.glyphicon-bitcoin:before {
  content: "\e227";
}
.glyphicon-btc:before {
  content: "\e227";
}
.glyphicon-xbt:before {
  content: "\e227";
}
.glyphicon-yen:before {
  content: "\00a5";
}
.glyphicon-jpy:before {
  content: "\00a5";
}
.glyphicon-ruble:before {
  content: "\20bd";
}
.glyphicon-rub:before {
  content: "\20bd";
}
.glyphicon-scale:before {
  content: "\e230";
}
.glyphicon-ice-lolly:before {
  content: "\e231";
}
.glyphicon-ice-lolly-tasted:before {
  content: "\e232";
}
.glyphicon-education:before {
  content: "\e233";
}
.glyphicon-option-horizontal:before {
  content: "\e234";
}
.glyphicon-option-vertical:before {
  content: "\e235";
}
.glyphicon-menu-hamburger:before {
  content: "\e236";
}
.glyphicon-modal-window:before {
  content: "\e237";
}
.glyphicon-oil:before {
  content: "\e238";
}
.glyphicon-grain:before {
  content: "\e239";
}
.glyphicon-sunglasses:before {
  content: "\e240";
}
.glyphicon-text-size:before {
  content: "\e241";
}
.glyphicon-text-color:before {
  content: "\e242";
}
.glyphicon-text-background:before {
  content: "\e243";
}
.glyphicon-object-align-top:before {
  content: "\e244";
}
.glyphicon-object-align-bottom:before {
  content: "\e245";
}
.glyphicon-object-align-horizontal:before {
  content: "\e246";
}
.glyphicon-object-align-left:before {
  content: "\e247";
}
.glyphicon-object-align-vertical:before {
  content: "\e248";
}
.glyphicon-object-align-right:before {
  content: "\e249";
}
.glyphicon-triangle-right:before {
  content: "\e250";
}
.glyphicon-triangle-left:before {
  content: "\e251";
}
.glyphicon-triangle-bottom:before {
  content: "\e252";
}
.glyphicon-triangle-top:before {
  content: "\e253";
}
.glyphicon-console:before {
  content: "\e254";
}
.glyphicon-superscript:before {
  content: "\e255";
}
.glyphicon-subscript:before {
  content: "\e256";
}
.glyphicon-menu-left:before {
  content: "\e257";
}
.glyphicon-menu-right:before {
  content: "\e258";
}
.glyphicon-menu-down:before {
  content: "\e259";
}
.glyphicon-menu-up:before {
  content: "\e260";
}
* {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
*:before,
*:after {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
html {
  font-size: 10px;
  -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
}
body {
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-size: 13px;
  line-height: 1.42857143;
  color: #000;
  background-color: #fff;
}
input,
button,
select,
textarea {
  font-family: inherit;
  font-size: inherit;
  line-height: inherit;
}
a {
  color: #337ab7;
  text-decoration: none;
}
a:hover,
a:focus {
  color: #23527c;
  text-decoration: underline;
}
a:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
figure {
  margin: 0;
}
img {
  vertical-align: middle;
}
.img-responsive,
.thumbnail > img,
.thumbnail a > img,
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  display: block;
  max-width: 100%;
  height: auto;
}
.img-rounded {
  border-radius: 3px;
}
.img-thumbnail {
  padding: 4px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: all 0.2s ease-in-out;
  -o-transition: all 0.2s ease-in-out;
  transition: all 0.2s ease-in-out;
  display: inline-block;
  max-width: 100%;
  height: auto;
}
.img-circle {
  border-radius: 50%;
}
hr {
  margin-top: 18px;
  margin-bottom: 18px;
  border: 0;
  border-top: 1px solid #eeeeee;
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  padding: 0;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
[role="button"] {
  cursor: pointer;
}
h1,
h2,
h3,
h4,
h5,
h6,
.h1,
.h2,
.h3,
.h4,
.h5,
.h6 {
  font-family: inherit;
  font-weight: 500;
  line-height: 1.1;
  color: inherit;
}
h1 small,
h2 small,
h3 small,
h4 small,
h5 small,
h6 small,
.h1 small,
.h2 small,
.h3 small,
.h4 small,
.h5 small,
.h6 small,
h1 .small,
h2 .small,
h3 .small,
h4 .small,
h5 .small,
h6 .small,
.h1 .small,
.h2 .small,
.h3 .small,
.h4 .small,
.h5 .small,
.h6 .small {
  font-weight: normal;
  line-height: 1;
  color: #777777;
}
h1,
.h1,
h2,
.h2,
h3,
.h3 {
  margin-top: 18px;
  margin-bottom: 9px;
}
h1 small,
.h1 small,
h2 small,
.h2 small,
h3 small,
.h3 small,
h1 .small,
.h1 .small,
h2 .small,
.h2 .small,
h3 .small,
.h3 .small {
  font-size: 65%;
}
h4,
.h4,
h5,
.h5,
h6,
.h6 {
  margin-top: 9px;
  margin-bottom: 9px;
}
h4 small,
.h4 small,
h5 small,
.h5 small,
h6 small,
.h6 small,
h4 .small,
.h4 .small,
h5 .small,
.h5 .small,
h6 .small,
.h6 .small {
  font-size: 75%;
}
h1,
.h1 {
  font-size: 33px;
}
h2,
.h2 {
  font-size: 27px;
}
h3,
.h3 {
  font-size: 23px;
}
h4,
.h4 {
  font-size: 17px;
}
h5,
.h5 {
  font-size: 13px;
}
h6,
.h6 {
  font-size: 12px;
}
p {
  margin: 0 0 9px;
}
.lead {
  margin-bottom: 18px;
  font-size: 14px;
  font-weight: 300;
  line-height: 1.4;
}
@media (min-width: 768px) {
  .lead {
    font-size: 19.5px;
  }
}
small,
.small {
  font-size: 92%;
}
mark,
.mark {
  background-color: #fcf8e3;
  padding: .2em;
}
.text-left {
  text-align: left;
}
.text-right {
  text-align: right;
}
.text-center {
  text-align: center;
}
.text-justify {
  text-align: justify;
}
.text-nowrap {
  white-space: nowrap;
}
.text-lowercase {
  text-transform: lowercase;
}
.text-uppercase {
  text-transform: uppercase;
}
.text-capitalize {
  text-transform: capitalize;
}
.text-muted {
  color: #777777;
}
.text-primary {
  color: #337ab7;
}
a.text-primary:hover,
a.text-primary:focus {
  color: #286090;
}
.text-success {
  color: #3c763d;
}
a.text-success:hover,
a.text-success:focus {
  color: #2b542c;
}
.text-info {
  color: #31708f;
}
a.text-info:hover,
a.text-info:focus {
  color: #245269;
}
.text-warning {
  color: #8a6d3b;
}
a.text-warning:hover,
a.text-warning:focus {
  color: #66512c;
}
.text-danger {
  color: #a94442;
}
a.text-danger:hover,
a.text-danger:focus {
  color: #843534;
}
.bg-primary {
  color: #fff;
  background-color: #337ab7;
}
a.bg-primary:hover,
a.bg-primary:focus {
  background-color: #286090;
}
.bg-success {
  background-color: #dff0d8;
}
a.bg-success:hover,
a.bg-success:focus {
  background-color: #c1e2b3;
}
.bg-info {
  background-color: #d9edf7;
}
a.bg-info:hover,
a.bg-info:focus {
  background-color: #afd9ee;
}
.bg-warning {
  background-color: #fcf8e3;
}
a.bg-warning:hover,
a.bg-warning:focus {
  background-color: #f7ecb5;
}
.bg-danger {
  background-color: #f2dede;
}
a.bg-danger:hover,
a.bg-danger:focus {
  background-color: #e4b9b9;
}
.page-header {
  padding-bottom: 8px;
  margin: 36px 0 18px;
  border-bottom: 1px solid #eeeeee;
}
ul,
ol {
  margin-top: 0;
  margin-bottom: 9px;
}
ul ul,
ol ul,
ul ol,
ol ol {
  margin-bottom: 0;
}
.list-unstyled {
  padding-left: 0;
  list-style: none;
}
.list-inline {
  padding-left: 0;
  list-style: none;
  margin-left: -5px;
}
.list-inline > li {
  display: inline-block;
  padding-left: 5px;
  padding-right: 5px;
}
dl {
  margin-top: 0;
  margin-bottom: 18px;
}
dt,
dd {
  line-height: 1.42857143;
}
dt {
  font-weight: bold;
}
dd {
  margin-left: 0;
}
@media (min-width: 541px) {
  .dl-horizontal dt {
    float: left;
    width: 160px;
    clear: left;
    text-align: right;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }
  .dl-horizontal dd {
    margin-left: 180px;
  }
}
abbr[title],
abbr[data-original-title] {
  cursor: help;
  border-bottom: 1px dotted #777777;
}
.initialism {
  font-size: 90%;
  text-transform: uppercase;
}
blockquote {
  padding: 9px 18px;
  margin: 0 0 18px;
  font-size: inherit;
  border-left: 5px solid #eeeeee;
}
blockquote p:last-child,
blockquote ul:last-child,
blockquote ol:last-child {
  margin-bottom: 0;
}
blockquote footer,
blockquote small,
blockquote .small {
  display: block;
  font-size: 80%;
  line-height: 1.42857143;
  color: #777777;
}
blockquote footer:before,
blockquote small:before,
blockquote .small:before {
  content: '\2014 \00A0';
}
.blockquote-reverse,
blockquote.pull-right {
  padding-right: 15px;
  padding-left: 0;
  border-right: 5px solid #eeeeee;
  border-left: 0;
  text-align: right;
}
.blockquote-reverse footer:before,
blockquote.pull-right footer:before,
.blockquote-reverse small:before,
blockquote.pull-right small:before,
.blockquote-reverse .small:before,
blockquote.pull-right .small:before {
  content: '';
}
.blockquote-reverse footer:after,
blockquote.pull-right footer:after,
.blockquote-reverse small:after,
blockquote.pull-right small:after,
.blockquote-reverse .small:after,
blockquote.pull-right .small:after {
  content: '\00A0 \2014';
}
address {
  margin-bottom: 18px;
  font-style: normal;
  line-height: 1.42857143;
}
code,
kbd,
pre,
samp {
  font-family: monospace;
}
code {
  padding: 2px 4px;
  font-size: 90%;
  color: #c7254e;
  background-color: #f9f2f4;
  border-radius: 2px;
}
kbd {
  padding: 2px 4px;
  font-size: 90%;
  color: #888;
  background-color: transparent;
  border-radius: 1px;
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.25);
}
kbd kbd {
  padding: 0;
  font-size: 100%;
  font-weight: bold;
  box-shadow: none;
}
pre {
  display: block;
  padding: 8.5px;
  margin: 0 0 9px;
  font-size: 12px;
  line-height: 1.42857143;
  word-break: break-all;
  word-wrap: break-word;
  color: #333333;
  background-color: #f5f5f5;
  border: 1px solid #ccc;
  border-radius: 2px;
}
pre code {
  padding: 0;
  font-size: inherit;
  color: inherit;
  white-space: pre-wrap;
  background-color: transparent;
  border-radius: 0;
}
.pre-scrollable {
  max-height: 340px;
  overflow-y: scroll;
}
.container {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
@media (min-width: 768px) {
  .container {
    width: 768px;
  }
}
@media (min-width: 992px) {
  .container {
    width: 940px;
  }
}
@media (min-width: 1200px) {
  .container {
    width: 1140px;
  }
}
.container-fluid {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
.row {
  margin-left: 0px;
  margin-right: 0px;
}
.col-xs-1, .col-sm-1, .col-md-1, .col-lg-1, .col-xs-2, .col-sm-2, .col-md-2, .col-lg-2, .col-xs-3, .col-sm-3, .col-md-3, .col-lg-3, .col-xs-4, .col-sm-4, .col-md-4, .col-lg-4, .col-xs-5, .col-sm-5, .col-md-5, .col-lg-5, .col-xs-6, .col-sm-6, .col-md-6, .col-lg-6, .col-xs-7, .col-sm-7, .col-md-7, .col-lg-7, .col-xs-8, .col-sm-8, .col-md-8, .col-lg-8, .col-xs-9, .col-sm-9, .col-md-9, .col-lg-9, .col-xs-10, .col-sm-10, .col-md-10, .col-lg-10, .col-xs-11, .col-sm-11, .col-md-11, .col-lg-11, .col-xs-12, .col-sm-12, .col-md-12, .col-lg-12 {
  position: relative;
  min-height: 1px;
  padding-left: 0px;
  padding-right: 0px;
}
.col-xs-1, .col-xs-2, .col-xs-3, .col-xs-4, .col-xs-5, .col-xs-6, .col-xs-7, .col-xs-8, .col-xs-9, .col-xs-10, .col-xs-11, .col-xs-12 {
  float: left;
}
.col-xs-12 {
  width: 100%;
}
.col-xs-11 {
  width: 91.66666667%;
}
.col-xs-10 {
  width: 83.33333333%;
}
.col-xs-9 {
  width: 75%;
}
.col-xs-8 {
  width: 66.66666667%;
}
.col-xs-7 {
  width: 58.33333333%;
}
.col-xs-6 {
  width: 50%;
}
.col-xs-5 {
  width: 41.66666667%;
}
.col-xs-4 {
  width: 33.33333333%;
}
.col-xs-3 {
  width: 25%;
}
.col-xs-2 {
  width: 16.66666667%;
}
.col-xs-1 {
  width: 8.33333333%;
}
.col-xs-pull-12 {
  right: 100%;
}
.col-xs-pull-11 {
  right: 91.66666667%;
}
.col-xs-pull-10 {
  right: 83.33333333%;
}
.col-xs-pull-9 {
  right: 75%;
}
.col-xs-pull-8 {
  right: 66.66666667%;
}
.col-xs-pull-7 {
  right: 58.33333333%;
}
.col-xs-pull-6 {
  right: 50%;
}
.col-xs-pull-5 {
  right: 41.66666667%;
}
.col-xs-pull-4 {
  right: 33.33333333%;
}
.col-xs-pull-3 {
  right: 25%;
}
.col-xs-pull-2 {
  right: 16.66666667%;
}
.col-xs-pull-1 {
  right: 8.33333333%;
}
.col-xs-pull-0 {
  right: auto;
}
.col-xs-push-12 {
  left: 100%;
}
.col-xs-push-11 {
  left: 91.66666667%;
}
.col-xs-push-10 {
  left: 83.33333333%;
}
.col-xs-push-9 {
  left: 75%;
}
.col-xs-push-8 {
  left: 66.66666667%;
}
.col-xs-push-7 {
  left: 58.33333333%;
}
.col-xs-push-6 {
  left: 50%;
}
.col-xs-push-5 {
  left: 41.66666667%;
}
.col-xs-push-4 {
  left: 33.33333333%;
}
.col-xs-push-3 {
  left: 25%;
}
.col-xs-push-2 {
  left: 16.66666667%;
}
.col-xs-push-1 {
  left: 8.33333333%;
}
.col-xs-push-0 {
  left: auto;
}
.col-xs-offset-12 {
  margin-left: 100%;
}
.col-xs-offset-11 {
  margin-left: 91.66666667%;
}
.col-xs-offset-10 {
  margin-left: 83.33333333%;
}
.col-xs-offset-9 {
  margin-left: 75%;
}
.col-xs-offset-8 {
  margin-left: 66.66666667%;
}
.col-xs-offset-7 {
  margin-left: 58.33333333%;
}
.col-xs-offset-6 {
  margin-left: 50%;
}
.col-xs-offset-5 {
  margin-left: 41.66666667%;
}
.col-xs-offset-4 {
  margin-left: 33.33333333%;
}
.col-xs-offset-3 {
  margin-left: 25%;
}
.col-xs-offset-2 {
  margin-left: 16.66666667%;
}
.col-xs-offset-1 {
  margin-left: 8.33333333%;
}
.col-xs-offset-0 {
  margin-left: 0%;
}
@media (min-width: 768px) {
  .col-sm-1, .col-sm-2, .col-sm-3, .col-sm-4, .col-sm-5, .col-sm-6, .col-sm-7, .col-sm-8, .col-sm-9, .col-sm-10, .col-sm-11, .col-sm-12 {
    float: left;
  }
  .col-sm-12 {
    width: 100%;
  }
  .col-sm-11 {
    width: 91.66666667%;
  }
  .col-sm-10 {
    width: 83.33333333%;
  }
  .col-sm-9 {
    width: 75%;
  }
  .col-sm-8 {
    width: 66.66666667%;
  }
  .col-sm-7 {
    width: 58.33333333%;
  }
  .col-sm-6 {
    width: 50%;
  }
  .col-sm-5 {
    width: 41.66666667%;
  }
  .col-sm-4 {
    width: 33.33333333%;
  }
  .col-sm-3 {
    width: 25%;
  }
  .col-sm-2 {
    width: 16.66666667%;
  }
  .col-sm-1 {
    width: 8.33333333%;
  }
  .col-sm-pull-12 {
    right: 100%;
  }
  .col-sm-pull-11 {
    right: 91.66666667%;
  }
  .col-sm-pull-10 {
    right: 83.33333333%;
  }
  .col-sm-pull-9 {
    right: 75%;
  }
  .col-sm-pull-8 {
    right: 66.66666667%;
  }
  .col-sm-pull-7 {
    right: 58.33333333%;
  }
  .col-sm-pull-6 {
    right: 50%;
  }
  .col-sm-pull-5 {
    right: 41.66666667%;
  }
  .col-sm-pull-4 {
    right: 33.33333333%;
  }
  .col-sm-pull-3 {
    right: 25%;
  }
  .col-sm-pull-2 {
    right: 16.66666667%;
  }
  .col-sm-pull-1 {
    right: 8.33333333%;
  }
  .col-sm-pull-0 {
    right: auto;
  }
  .col-sm-push-12 {
    left: 100%;
  }
  .col-sm-push-11 {
    left: 91.66666667%;
  }
  .col-sm-push-10 {
    left: 83.33333333%;
  }
  .col-sm-push-9 {
    left: 75%;
  }
  .col-sm-push-8 {
    left: 66.66666667%;
  }
  .col-sm-push-7 {
    left: 58.33333333%;
  }
  .col-sm-push-6 {
    left: 50%;
  }
  .col-sm-push-5 {
    left: 41.66666667%;
  }
  .col-sm-push-4 {
    left: 33.33333333%;
  }
  .col-sm-push-3 {
    left: 25%;
  }
  .col-sm-push-2 {
    left: 16.66666667%;
  }
  .col-sm-push-1 {
    left: 8.33333333%;
  }
  .col-sm-push-0 {
    left: auto;
  }
  .col-sm-offset-12 {
    margin-left: 100%;
  }
  .col-sm-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-sm-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-sm-offset-9 {
    margin-left: 75%;
  }
  .col-sm-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-sm-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-sm-offset-6 {
    margin-left: 50%;
  }
  .col-sm-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-sm-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-sm-offset-3 {
    margin-left: 25%;
  }
  .col-sm-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-sm-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-sm-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 992px) {
  .col-md-1, .col-md-2, .col-md-3, .col-md-4, .col-md-5, .col-md-6, .col-md-7, .col-md-8, .col-md-9, .col-md-10, .col-md-11, .col-md-12 {
    float: left;
  }
  .col-md-12 {
    width: 100%;
  }
  .col-md-11 {
    width: 91.66666667%;
  }
  .col-md-10 {
    width: 83.33333333%;
  }
  .col-md-9 {
    width: 75%;
  }
  .col-md-8 {
    width: 66.66666667%;
  }
  .col-md-7 {
    width: 58.33333333%;
  }
  .col-md-6 {
    width: 50%;
  }
  .col-md-5 {
    width: 41.66666667%;
  }
  .col-md-4 {
    width: 33.33333333%;
  }
  .col-md-3 {
    width: 25%;
  }
  .col-md-2 {
    width: 16.66666667%;
  }
  .col-md-1 {
    width: 8.33333333%;
  }
  .col-md-pull-12 {
    right: 100%;
  }
  .col-md-pull-11 {
    right: 91.66666667%;
  }
  .col-md-pull-10 {
    right: 83.33333333%;
  }
  .col-md-pull-9 {
    right: 75%;
  }
  .col-md-pull-8 {
    right: 66.66666667%;
  }
  .col-md-pull-7 {
    right: 58.33333333%;
  }
  .col-md-pull-6 {
    right: 50%;
  }
  .col-md-pull-5 {
    right: 41.66666667%;
  }
  .col-md-pull-4 {
    right: 33.33333333%;
  }
  .col-md-pull-3 {
    right: 25%;
  }
  .col-md-pull-2 {
    right: 16.66666667%;
  }
  .col-md-pull-1 {
    right: 8.33333333%;
  }
  .col-md-pull-0 {
    right: auto;
  }
  .col-md-push-12 {
    left: 100%;
  }
  .col-md-push-11 {
    left: 91.66666667%;
  }
  .col-md-push-10 {
    left: 83.33333333%;
  }
  .col-md-push-9 {
    left: 75%;
  }
  .col-md-push-8 {
    left: 66.66666667%;
  }
  .col-md-push-7 {
    left: 58.33333333%;
  }
  .col-md-push-6 {
    left: 50%;
  }
  .col-md-push-5 {
    left: 41.66666667%;
  }
  .col-md-push-4 {
    left: 33.33333333%;
  }
  .col-md-push-3 {
    left: 25%;
  }
  .col-md-push-2 {
    left: 16.66666667%;
  }
  .col-md-push-1 {
    left: 8.33333333%;
  }
  .col-md-push-0 {
    left: auto;
  }
  .col-md-offset-12 {
    margin-left: 100%;
  }
  .col-md-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-md-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-md-offset-9 {
    margin-left: 75%;
  }
  .col-md-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-md-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-md-offset-6 {
    margin-left: 50%;
  }
  .col-md-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-md-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-md-offset-3 {
    margin-left: 25%;
  }
  .col-md-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-md-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-md-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 1200px) {
  .col-lg-1, .col-lg-2, .col-lg-3, .col-lg-4, .col-lg-5, .col-lg-6, .col-lg-7, .col-lg-8, .col-lg-9, .col-lg-10, .col-lg-11, .col-lg-12 {
    float: left;
  }
  .col-lg-12 {
    width: 100%;
  }
  .col-lg-11 {
    width: 91.66666667%;
  }
  .col-lg-10 {
    width: 83.33333333%;
  }
  .col-lg-9 {
    width: 75%;
  }
  .col-lg-8 {
    width: 66.66666667%;
  }
  .col-lg-7 {
    width: 58.33333333%;
  }
  .col-lg-6 {
    width: 50%;
  }
  .col-lg-5 {
    width: 41.66666667%;
  }
  .col-lg-4 {
    width: 33.33333333%;
  }
  .col-lg-3 {
    width: 25%;
  }
  .col-lg-2 {
    width: 16.66666667%;
  }
  .col-lg-1 {
    width: 8.33333333%;
  }
  .col-lg-pull-12 {
    right: 100%;
  }
  .col-lg-pull-11 {
    right: 91.66666667%;
  }
  .col-lg-pull-10 {
    right: 83.33333333%;
  }
  .col-lg-pull-9 {
    right: 75%;
  }
  .col-lg-pull-8 {
    right: 66.66666667%;
  }
  .col-lg-pull-7 {
    right: 58.33333333%;
  }
  .col-lg-pull-6 {
    right: 50%;
  }
  .col-lg-pull-5 {
    right: 41.66666667%;
  }
  .col-lg-pull-4 {
    right: 33.33333333%;
  }
  .col-lg-pull-3 {
    right: 25%;
  }
  .col-lg-pull-2 {
    right: 16.66666667%;
  }
  .col-lg-pull-1 {
    right: 8.33333333%;
  }
  .col-lg-pull-0 {
    right: auto;
  }
  .col-lg-push-12 {
    left: 100%;
  }
  .col-lg-push-11 {
    left: 91.66666667%;
  }
  .col-lg-push-10 {
    left: 83.33333333%;
  }
  .col-lg-push-9 {
    left: 75%;
  }
  .col-lg-push-8 {
    left: 66.66666667%;
  }
  .col-lg-push-7 {
    left: 58.33333333%;
  }
  .col-lg-push-6 {
    left: 50%;
  }
  .col-lg-push-5 {
    left: 41.66666667%;
  }
  .col-lg-push-4 {
    left: 33.33333333%;
  }
  .col-lg-push-3 {
    left: 25%;
  }
  .col-lg-push-2 {
    left: 16.66666667%;
  }
  .col-lg-push-1 {
    left: 8.33333333%;
  }
  .col-lg-push-0 {
    left: auto;
  }
  .col-lg-offset-12 {
    margin-left: 100%;
  }
  .col-lg-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-lg-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-lg-offset-9 {
    margin-left: 75%;
  }
  .col-lg-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-lg-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-lg-offset-6 {
    margin-left: 50%;
  }
  .col-lg-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-lg-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-lg-offset-3 {
    margin-left: 25%;
  }
  .col-lg-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-lg-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-lg-offset-0 {
    margin-left: 0%;
  }
}
table {
  background-color: transparent;
}
caption {
  padding-top: 8px;
  padding-bottom: 8px;
  color: #777777;
  text-align: left;
}
th {
  text-align: left;
}
.table {
  width: 100%;
  max-width: 100%;
  margin-bottom: 18px;
}
.table > thead > tr > th,
.table > tbody > tr > th,
.table > tfoot > tr > th,
.table > thead > tr > td,
.table > tbody > tr > td,
.table > tfoot > tr > td {
  padding: 8px;
  line-height: 1.42857143;
  vertical-align: top;
  border-top: 1px solid #ddd;
}
.table > thead > tr > th {
  vertical-align: bottom;
  border-bottom: 2px solid #ddd;
}
.table > caption + thead > tr:first-child > th,
.table > colgroup + thead > tr:first-child > th,
.table > thead:first-child > tr:first-child > th,
.table > caption + thead > tr:first-child > td,
.table > colgroup + thead > tr:first-child > td,
.table > thead:first-child > tr:first-child > td {
  border-top: 0;
}
.table > tbody + tbody {
  border-top: 2px solid #ddd;
}
.table .table {
  background-color: #fff;
}
.table-condensed > thead > tr > th,
.table-condensed > tbody > tr > th,
.table-condensed > tfoot > tr > th,
.table-condensed > thead > tr > td,
.table-condensed > tbody > tr > td,
.table-condensed > tfoot > tr > td {
  padding: 5px;
}
.table-bordered {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > tbody > tr > th,
.table-bordered > tfoot > tr > th,
.table-bordered > thead > tr > td,
.table-bordered > tbody > tr > td,
.table-bordered > tfoot > tr > td {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > thead > tr > td {
  border-bottom-width: 2px;
}
.table-striped > tbody > tr:nth-of-type(odd) {
  background-color: #f9f9f9;
}
.table-hover > tbody > tr:hover {
  background-color: #f5f5f5;
}
table col[class*="col-"] {
  position: static;
  float: none;
  display: table-column;
}
table td[class*="col-"],
table th[class*="col-"] {
  position: static;
  float: none;
  display: table-cell;
}
.table > thead > tr > td.active,
.table > tbody > tr > td.active,
.table > tfoot > tr > td.active,
.table > thead > tr > th.active,
.table > tbody > tr > th.active,
.table > tfoot > tr > th.active,
.table > thead > tr.active > td,
.table > tbody > tr.active > td,
.table > tfoot > tr.active > td,
.table > thead > tr.active > th,
.table > tbody > tr.active > th,
.table > tfoot > tr.active > th {
  background-color: #f5f5f5;
}
.table-hover > tbody > tr > td.active:hover,
.table-hover > tbody > tr > th.active:hover,
.table-hover > tbody > tr.active:hover > td,
.table-hover > tbody > tr:hover > .active,
.table-hover > tbody > tr.active:hover > th {
  background-color: #e8e8e8;
}
.table > thead > tr > td.success,
.table > tbody > tr > td.success,
.table > tfoot > tr > td.success,
.table > thead > tr > th.success,
.table > tbody > tr > th.success,
.table > tfoot > tr > th.success,
.table > thead > tr.success > td,
.table > tbody > tr.success > td,
.table > tfoot > tr.success > td,
.table > thead > tr.success > th,
.table > tbody > tr.success > th,
.table > tfoot > tr.success > th {
  background-color: #dff0d8;
}
.table-hover > tbody > tr > td.success:hover,
.table-hover > tbody > tr > th.success:hover,
.table-hover > tbody > tr.success:hover > td,
.table-hover > tbody > tr:hover > .success,
.table-hover > tbody > tr.success:hover > th {
  background-color: #d0e9c6;
}
.table > thead > tr > td.info,
.table > tbody > tr > td.info,
.table > tfoot > tr > td.info,
.table > thead > tr > th.info,
.table > tbody > tr > th.info,
.table > tfoot > tr > th.info,
.table > thead > tr.info > td,
.table > tbody > tr.info > td,
.table > tfoot > tr.info > td,
.table > thead > tr.info > th,
.table > tbody > tr.info > th,
.table > tfoot > tr.info > th {
  background-color: #d9edf7;
}
.table-hover > tbody > tr > td.info:hover,
.table-hover > tbody > tr > th.info:hover,
.table-hover > tbody > tr.info:hover > td,
.table-hover > tbody > tr:hover > .info,
.table-hover > tbody > tr.info:hover > th {
  background-color: #c4e3f3;
}
.table > thead > tr > td.warning,
.table > tbody > tr > td.warning,
.table > tfoot > tr > td.warning,
.table > thead > tr > th.warning,
.table > tbody > tr > th.warning,
.table > tfoot > tr > th.warning,
.table > thead > tr.warning > td,
.table > tbody > tr.warning > td,
.table > tfoot > tr.warning > td,
.table > thead > tr.warning > th,
.table > tbody > tr.warning > th,
.table > tfoot > tr.warning > th {
  background-color: #fcf8e3;
}
.table-hover > tbody > tr > td.warning:hover,
.table-hover > tbody > tr > th.warning:hover,
.table-hover > tbody > tr.warning:hover > td,
.table-hover > tbody > tr:hover > .warning,
.table-hover > tbody > tr.warning:hover > th {
  background-color: #faf2cc;
}
.table > thead > tr > td.danger,
.table > tbody > tr > td.danger,
.table > tfoot > tr > td.danger,
.table > thead > tr > th.danger,
.table > tbody > tr > th.danger,
.table > tfoot > tr > th.danger,
.table > thead > tr.danger > td,
.table > tbody > tr.danger > td,
.table > tfoot > tr.danger > td,
.table > thead > tr.danger > th,
.table > tbody > tr.danger > th,
.table > tfoot > tr.danger > th {
  background-color: #f2dede;
}
.table-hover > tbody > tr > td.danger:hover,
.table-hover > tbody > tr > th.danger:hover,
.table-hover > tbody > tr.danger:hover > td,
.table-hover > tbody > tr:hover > .danger,
.table-hover > tbody > tr.danger:hover > th {
  background-color: #ebcccc;
}
.table-responsive {
  overflow-x: auto;
  min-height: 0.01%;
}
@media screen and (max-width: 767px) {
  .table-responsive {
    width: 100%;
    margin-bottom: 13.5px;
    overflow-y: hidden;
    -ms-overflow-style: -ms-autohiding-scrollbar;
    border: 1px solid #ddd;
  }
  .table-responsive > .table {
    margin-bottom: 0;
  }
  .table-responsive > .table > thead > tr > th,
  .table-responsive > .table > tbody > tr > th,
  .table-responsive > .table > tfoot > tr > th,
  .table-responsive > .table > thead > tr > td,
  .table-responsive > .table > tbody > tr > td,
  .table-responsive > .table > tfoot > tr > td {
    white-space: nowrap;
  }
  .table-responsive > .table-bordered {
    border: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:first-child,
  .table-responsive > .table-bordered > tbody > tr > th:first-child,
  .table-responsive > .table-bordered > tfoot > tr > th:first-child,
  .table-responsive > .table-bordered > thead > tr > td:first-child,
  .table-responsive > .table-bordered > tbody > tr > td:first-child,
  .table-responsive > .table-bordered > tfoot > tr > td:first-child {
    border-left: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:last-child,
  .table-responsive > .table-bordered > tbody > tr > th:last-child,
  .table-responsive > .table-bordered > tfoot > tr > th:last-child,
  .table-responsive > .table-bordered > thead > tr > td:last-child,
  .table-responsive > .table-bordered > tbody > tr > td:last-child,
  .table-responsive > .table-bordered > tfoot > tr > td:last-child {
    border-right: 0;
  }
  .table-responsive > .table-bordered > tbody > tr:last-child > th,
  .table-responsive > .table-bordered > tfoot > tr:last-child > th,
  .table-responsive > .table-bordered > tbody > tr:last-child > td,
  .table-responsive > .table-bordered > tfoot > tr:last-child > td {
    border-bottom: 0;
  }
}
fieldset {
  padding: 0;
  margin: 0;
  border: 0;
  min-width: 0;
}
legend {
  display: block;
  width: 100%;
  padding: 0;
  margin-bottom: 18px;
  font-size: 19.5px;
  line-height: inherit;
  color: #333333;
  border: 0;
  border-bottom: 1px solid #e5e5e5;
}
label {
  display: inline-block;
  max-width: 100%;
  margin-bottom: 5px;
  font-weight: bold;
}
input[type="search"] {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
input[type="radio"],
input[type="checkbox"] {
  margin: 4px 0 0;
  margin-top: 1px \9;
  line-height: normal;
}
input[type="file"] {
  display: block;
}
input[type="range"] {
  display: block;
  width: 100%;
}
select[multiple],
select[size] {
  height: auto;
}
input[type="file"]:focus,
input[type="radio"]:focus,
input[type="checkbox"]:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
output {
  display: block;
  padding-top: 7px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
}
.form-control {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
}
.form-control:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.form-control::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.form-control:-ms-input-placeholder {
  color: #999;
}
.form-control::-webkit-input-placeholder {
  color: #999;
}
.form-control::-ms-expand {
  border: 0;
  background-color: transparent;
}
.form-control[disabled],
.form-control[readonly],
fieldset[disabled] .form-control {
  background-color: #eeeeee;
  opacity: 1;
}
.form-control[disabled],
fieldset[disabled] .form-control {
  cursor: not-allowed;
}
textarea.form-control {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: none;
}
@media screen and (-webkit-min-device-pixel-ratio: 0) {
  input[type="date"].form-control,
  input[type="time"].form-control,
  input[type="datetime-local"].form-control,
  input[type="month"].form-control {
    line-height: 32px;
  }
  input[type="date"].input-sm,
  input[type="time"].input-sm,
  input[type="datetime-local"].input-sm,
  input[type="month"].input-sm,
  .input-group-sm input[type="date"],
  .input-group-sm input[type="time"],
  .input-group-sm input[type="datetime-local"],
  .input-group-sm input[type="month"] {
    line-height: 30px;
  }
  input[type="date"].input-lg,
  input[type="time"].input-lg,
  input[type="datetime-local"].input-lg,
  input[type="month"].input-lg,
  .input-group-lg input[type="date"],
  .input-group-lg input[type="time"],
  .input-group-lg input[type="datetime-local"],
  .input-group-lg input[type="month"] {
    line-height: 45px;
  }
}
.form-group {
  margin-bottom: 15px;
}
.radio,
.checkbox {
  position: relative;
  display: block;
  margin-top: 10px;
  margin-bottom: 10px;
}
.radio label,
.checkbox label {
  min-height: 18px;
  padding-left: 20px;
  margin-bottom: 0;
  font-weight: normal;
  cursor: pointer;
}
.radio input[type="radio"],
.radio-inline input[type="radio"],
.checkbox input[type="checkbox"],
.checkbox-inline input[type="checkbox"] {
  position: absolute;
  margin-left: -20px;
  margin-top: 4px \9;
}
.radio + .radio,
.checkbox + .checkbox {
  margin-top: -5px;
}
.radio-inline,
.checkbox-inline {
  position: relative;
  display: inline-block;
  padding-left: 20px;
  margin-bottom: 0;
  vertical-align: middle;
  font-weight: normal;
  cursor: pointer;
}
.radio-inline + .radio-inline,
.checkbox-inline + .checkbox-inline {
  margin-top: 0;
  margin-left: 10px;
}
input[type="radio"][disabled],
input[type="checkbox"][disabled],
input[type="radio"].disabled,
input[type="checkbox"].disabled,
fieldset[disabled] input[type="radio"],
fieldset[disabled] input[type="checkbox"] {
  cursor: not-allowed;
}
.radio-inline.disabled,
.checkbox-inline.disabled,
fieldset[disabled] .radio-inline,
fieldset[disabled] .checkbox-inline {
  cursor: not-allowed;
}
.radio.disabled label,
.checkbox.disabled label,
fieldset[disabled] .radio label,
fieldset[disabled] .checkbox label {
  cursor: not-allowed;
}
.form-control-static {
  padding-top: 7px;
  padding-bottom: 7px;
  margin-bottom: 0;
  min-height: 31px;
}
.form-control-static.input-lg,
.form-control-static.input-sm {
  padding-left: 0;
  padding-right: 0;
}
.input-sm {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-sm {
  height: 30px;
  line-height: 30px;
}
textarea.input-sm,
select[multiple].input-sm {
  height: auto;
}
.form-group-sm .form-control {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.form-group-sm select.form-control {
  height: 30px;
  line-height: 30px;
}
.form-group-sm textarea.form-control,
.form-group-sm select[multiple].form-control {
  height: auto;
}
.form-group-sm .form-control-static {
  height: 30px;
  min-height: 30px;
  padding: 6px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.input-lg {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-lg {
  height: 45px;
  line-height: 45px;
}
textarea.input-lg,
select[multiple].input-lg {
  height: auto;
}
.form-group-lg .form-control {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.form-group-lg select.form-control {
  height: 45px;
  line-height: 45px;
}
.form-group-lg textarea.form-control,
.form-group-lg select[multiple].form-control {
  height: auto;
}
.form-group-lg .form-control-static {
  height: 45px;
  min-height: 35px;
  padding: 11px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.has-feedback {
  position: relative;
}
.has-feedback .form-control {
  padding-right: 40px;
}
.form-control-feedback {
  position: absolute;
  top: 0;
  right: 0;
  z-index: 2;
  display: block;
  width: 32px;
  height: 32px;
  line-height: 32px;
  text-align: center;
  pointer-events: none;
}
.input-lg + .form-control-feedback,
.input-group-lg + .form-control-feedback,
.form-group-lg .form-control + .form-control-feedback {
  width: 45px;
  height: 45px;
  line-height: 45px;
}
.input-sm + .form-control-feedback,
.input-group-sm + .form-control-feedback,
.form-group-sm .form-control + .form-control-feedback {
  width: 30px;
  height: 30px;
  line-height: 30px;
}
.has-success .help-block,
.has-success .control-label,
.has-success .radio,
.has-success .checkbox,
.has-success .radio-inline,
.has-success .checkbox-inline,
.has-success.radio label,
.has-success.checkbox label,
.has-success.radio-inline label,
.has-success.checkbox-inline label {
  color: #3c763d;
}
.has-success .form-control {
  border-color: #3c763d;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-success .form-control:focus {
  border-color: #2b542c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
}
.has-success .input-group-addon {
  color: #3c763d;
  border-color: #3c763d;
  background-color: #dff0d8;
}
.has-success .form-control-feedback {
  color: #3c763d;
}
.has-warning .help-block,
.has-warning .control-label,
.has-warning .radio,
.has-warning .checkbox,
.has-warning .radio-inline,
.has-warning .checkbox-inline,
.has-warning.radio label,
.has-warning.checkbox label,
.has-warning.radio-inline label,
.has-warning.checkbox-inline label {
  color: #8a6d3b;
}
.has-warning .form-control {
  border-color: #8a6d3b;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-warning .form-control:focus {
  border-color: #66512c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
}
.has-warning .input-group-addon {
  color: #8a6d3b;
  border-color: #8a6d3b;
  background-color: #fcf8e3;
}
.has-warning .form-control-feedback {
  color: #8a6d3b;
}
.has-error .help-block,
.has-error .control-label,
.has-error .radio,
.has-error .checkbox,
.has-error .radio-inline,
.has-error .checkbox-inline,
.has-error.radio label,
.has-error.checkbox label,
.has-error.radio-inline label,
.has-error.checkbox-inline label {
  color: #a94442;
}
.has-error .form-control {
  border-color: #a94442;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-error .form-control:focus {
  border-color: #843534;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
}
.has-error .input-group-addon {
  color: #a94442;
  border-color: #a94442;
  background-color: #f2dede;
}
.has-error .form-control-feedback {
  color: #a94442;
}
.has-feedback label ~ .form-control-feedback {
  top: 23px;
}
.has-feedback label.sr-only ~ .form-control-feedback {
  top: 0;
}
.help-block {
  display: block;
  margin-top: 5px;
  margin-bottom: 10px;
  color: #404040;
}
@media (min-width: 768px) {
  .form-inline .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .form-inline .form-control-static {
    display: inline-block;
  }
  .form-inline .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .form-inline .input-group .input-group-addon,
  .form-inline .input-group .input-group-btn,
  .form-inline .input-group .form-control {
    width: auto;
  }
  .form-inline .input-group > .form-control {
    width: 100%;
  }
  .form-inline .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio,
  .form-inline .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio label,
  .form-inline .checkbox label {
    padding-left: 0;
  }
  .form-inline .radio input[type="radio"],
  .form-inline .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .form-inline .has-feedback .form-control-feedback {
    top: 0;
  }
}
.form-horizontal .radio,
.form-horizontal .checkbox,
.form-horizontal .radio-inline,
.form-horizontal .checkbox-inline {
  margin-top: 0;
  margin-bottom: 0;
  padding-top: 7px;
}
.form-horizontal .radio,
.form-horizontal .checkbox {
  min-height: 25px;
}
.form-horizontal .form-group {
  margin-left: 0px;
  margin-right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .control-label {
    text-align: right;
    margin-bottom: 0;
    padding-top: 7px;
  }
}
.form-horizontal .has-feedback .form-control-feedback {
  right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .form-group-lg .control-label {
    padding-top: 11px;
    font-size: 17px;
  }
}
@media (min-width: 768px) {
  .form-horizontal .form-group-sm .control-label {
    padding-top: 6px;
    font-size: 12px;
  }
}
.btn {
  display: inline-block;
  margin-bottom: 0;
  font-weight: normal;
  text-align: center;
  vertical-align: middle;
  touch-action: manipulation;
  cursor: pointer;
  background-image: none;
  border: 1px solid transparent;
  white-space: nowrap;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  border-radius: 2px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
.btn:focus,
.btn:active:focus,
.btn.active:focus,
.btn.focus,
.btn:active.focus,
.btn.active.focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
.btn:hover,
.btn:focus,
.btn.focus {
  color: #333;
  text-decoration: none;
}
.btn:active,
.btn.active {
  outline: 0;
  background-image: none;
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn.disabled,
.btn[disabled],
fieldset[disabled] .btn {
  cursor: not-allowed;
  opacity: 0.65;
  filter: alpha(opacity=65);
  -webkit-box-shadow: none;
  box-shadow: none;
}
a.btn.disabled,
fieldset[disabled] a.btn {
  pointer-events: none;
}
.btn-default {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.btn-default:focus,
.btn-default.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.btn-default:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active:hover,
.btn-default.active:hover,
.open > .dropdown-toggle.btn-default:hover,
.btn-default:active:focus,
.btn-default.active:focus,
.open > .dropdown-toggle.btn-default:focus,
.btn-default:active.focus,
.btn-default.active.focus,
.open > .dropdown-toggle.btn-default.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  background-image: none;
}
.btn-default.disabled:hover,
.btn-default[disabled]:hover,
fieldset[disabled] .btn-default:hover,
.btn-default.disabled:focus,
.btn-default[disabled]:focus,
fieldset[disabled] .btn-default:focus,
.btn-default.disabled.focus,
.btn-default[disabled].focus,
fieldset[disabled] .btn-default.focus {
  background-color: #fff;
  border-color: #ccc;
}
.btn-default .badge {
  color: #fff;
  background-color: #333;
}
.btn-primary {
  color: #fff;
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary:focus,
.btn-primary.focus {
  color: #fff;
  background-color: #286090;
  border-color: #122b40;
}
.btn-primary:hover {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active:hover,
.btn-primary.active:hover,
.open > .dropdown-toggle.btn-primary:hover,
.btn-primary:active:focus,
.btn-primary.active:focus,
.open > .dropdown-toggle.btn-primary:focus,
.btn-primary:active.focus,
.btn-primary.active.focus,
.open > .dropdown-toggle.btn-primary.focus {
  color: #fff;
  background-color: #204d74;
  border-color: #122b40;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  background-image: none;
}
.btn-primary.disabled:hover,
.btn-primary[disabled]:hover,
fieldset[disabled] .btn-primary:hover,
.btn-primary.disabled:focus,
.btn-primary[disabled]:focus,
fieldset[disabled] .btn-primary:focus,
.btn-primary.disabled.focus,
.btn-primary[disabled].focus,
fieldset[disabled] .btn-primary.focus {
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary .badge {
  color: #337ab7;
  background-color: #fff;
}
.btn-success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success:focus,
.btn-success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.btn-success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active:hover,
.btn-success.active:hover,
.open > .dropdown-toggle.btn-success:hover,
.btn-success:active:focus,
.btn-success.active:focus,
.open > .dropdown-toggle.btn-success:focus,
.btn-success:active.focus,
.btn-success.active.focus,
.open > .dropdown-toggle.btn-success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  background-image: none;
}
.btn-success.disabled:hover,
.btn-success[disabled]:hover,
fieldset[disabled] .btn-success:hover,
.btn-success.disabled:focus,
.btn-success[disabled]:focus,
fieldset[disabled] .btn-success:focus,
.btn-success.disabled.focus,
.btn-success[disabled].focus,
fieldset[disabled] .btn-success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.btn-info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info:focus,
.btn-info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.btn-info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active:hover,
.btn-info.active:hover,
.open > .dropdown-toggle.btn-info:hover,
.btn-info:active:focus,
.btn-info.active:focus,
.open > .dropdown-toggle.btn-info:focus,
.btn-info:active.focus,
.btn-info.active.focus,
.open > .dropdown-toggle.btn-info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  background-image: none;
}
.btn-info.disabled:hover,
.btn-info[disabled]:hover,
fieldset[disabled] .btn-info:hover,
.btn-info.disabled:focus,
.btn-info[disabled]:focus,
fieldset[disabled] .btn-info:focus,
.btn-info.disabled.focus,
.btn-info[disabled].focus,
fieldset[disabled] .btn-info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.btn-warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning:focus,
.btn-warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.btn-warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active:hover,
.btn-warning.active:hover,
.open > .dropdown-toggle.btn-warning:hover,
.btn-warning:active:focus,
.btn-warning.active:focus,
.open > .dropdown-toggle.btn-warning:focus,
.btn-warning:active.focus,
.btn-warning.active.focus,
.open > .dropdown-toggle.btn-warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  background-image: none;
}
.btn-warning.disabled:hover,
.btn-warning[disabled]:hover,
fieldset[disabled] .btn-warning:hover,
.btn-warning.disabled:focus,
.btn-warning[disabled]:focus,
fieldset[disabled] .btn-warning:focus,
.btn-warning.disabled.focus,
.btn-warning[disabled].focus,
fieldset[disabled] .btn-warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.btn-danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger:focus,
.btn-danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.btn-danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active:hover,
.btn-danger.active:hover,
.open > .dropdown-toggle.btn-danger:hover,
.btn-danger:active:focus,
.btn-danger.active:focus,
.open > .dropdown-toggle.btn-danger:focus,
.btn-danger:active.focus,
.btn-danger.active.focus,
.open > .dropdown-toggle.btn-danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  background-image: none;
}
.btn-danger.disabled:hover,
.btn-danger[disabled]:hover,
fieldset[disabled] .btn-danger:hover,
.btn-danger.disabled:focus,
.btn-danger[disabled]:focus,
fieldset[disabled] .btn-danger:focus,
.btn-danger.disabled.focus,
.btn-danger[disabled].focus,
fieldset[disabled] .btn-danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger .badge {
  color: #d9534f;
  background-color: #fff;
}
.btn-link {
  color: #337ab7;
  font-weight: normal;
  border-radius: 0;
}
.btn-link,
.btn-link:active,
.btn-link.active,
.btn-link[disabled],
fieldset[disabled] .btn-link {
  background-color: transparent;
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn-link,
.btn-link:hover,
.btn-link:focus,
.btn-link:active {
  border-color: transparent;
}
.btn-link:hover,
.btn-link:focus {
  color: #23527c;
  text-decoration: underline;
  background-color: transparent;
}
.btn-link[disabled]:hover,
fieldset[disabled] .btn-link:hover,
.btn-link[disabled]:focus,
fieldset[disabled] .btn-link:focus {
  color: #777777;
  text-decoration: none;
}
.btn-lg,
.btn-group-lg > .btn {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.btn-sm,
.btn-group-sm > .btn {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-xs,
.btn-group-xs > .btn {
  padding: 1px 5px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-block {
  display: block;
  width: 100%;
}
.btn-block + .btn-block {
  margin-top: 5px;
}
input[type="submit"].btn-block,
input[type="reset"].btn-block,
input[type="button"].btn-block {
  width: 100%;
}
.fade {
  opacity: 0;
  -webkit-transition: opacity 0.15s linear;
  -o-transition: opacity 0.15s linear;
  transition: opacity 0.15s linear;
}
.fade.in {
  opacity: 1;
}
.collapse {
  display: none;
}
.collapse.in {
  display: block;
}
tr.collapse.in {
  display: table-row;
}
tbody.collapse.in {
  display: table-row-group;
}
.collapsing {
  position: relative;
  height: 0;
  overflow: hidden;
  -webkit-transition-property: height, visibility;
  transition-property: height, visibility;
  -webkit-transition-duration: 0.35s;
  transition-duration: 0.35s;
  -webkit-transition-timing-function: ease;
  transition-timing-function: ease;
}
.caret {
  display: inline-block;
  width: 0;
  height: 0;
  margin-left: 2px;
  vertical-align: middle;
  border-top: 4px dashed;
  border-top: 4px solid \9;
  border-right: 4px solid transparent;
  border-left: 4px solid transparent;
}
.dropup,
.dropdown {
  position: relative;
}
.dropdown-toggle:focus {
  outline: 0;
}
.dropdown-menu {
  position: absolute;
  top: 100%;
  left: 0;
  z-index: 1000;
  display: none;
  float: left;
  min-width: 160px;
  padding: 5px 0;
  margin: 2px 0 0;
  list-style: none;
  font-size: 13px;
  text-align: left;
  background-color: #fff;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.15);
  border-radius: 2px;
  -webkit-box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  background-clip: padding-box;
}
.dropdown-menu.pull-right {
  right: 0;
  left: auto;
}
.dropdown-menu .divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.dropdown-menu > li > a {
  display: block;
  padding: 3px 20px;
  clear: both;
  font-weight: normal;
  line-height: 1.42857143;
  color: #333333;
  white-space: nowrap;
}
.dropdown-menu > li > a:hover,
.dropdown-menu > li > a:focus {
  text-decoration: none;
  color: #262626;
  background-color: #f5f5f5;
}
.dropdown-menu > .active > a,
.dropdown-menu > .active > a:hover,
.dropdown-menu > .active > a:focus {
  color: #fff;
  text-decoration: none;
  outline: 0;
  background-color: #337ab7;
}
.dropdown-menu > .disabled > a,
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  color: #777777;
}
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  text-decoration: none;
  background-color: transparent;
  background-image: none;
  filter: progid:DXImageTransform.Microsoft.gradient(enabled = false);
  cursor: not-allowed;
}
.open > .dropdown-menu {
  display: block;
}
.open > a {
  outline: 0;
}
.dropdown-menu-right {
  left: auto;
  right: 0;
}
.dropdown-menu-left {
  left: 0;
  right: auto;
}
.dropdown-header {
  display: block;
  padding: 3px 20px;
  font-size: 12px;
  line-height: 1.42857143;
  color: #777777;
  white-space: nowrap;
}
.dropdown-backdrop {
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
  top: 0;
  z-index: 990;
}
.pull-right > .dropdown-menu {
  right: 0;
  left: auto;
}
.dropup .caret,
.navbar-fixed-bottom .dropdown .caret {
  border-top: 0;
  border-bottom: 4px dashed;
  border-bottom: 4px solid \9;
  content: "";
}
.dropup .dropdown-menu,
.navbar-fixed-bottom .dropdown .dropdown-menu {
  top: auto;
  bottom: 100%;
  margin-bottom: 2px;
}
@media (min-width: 541px) {
  .navbar-right .dropdown-menu {
    left: auto;
    right: 0;
  }
  .navbar-right .dropdown-menu-left {
    left: 0;
    right: auto;
  }
}
.btn-group,
.btn-group-vertical {
  position: relative;
  display: inline-block;
  vertical-align: middle;
}
.btn-group > .btn,
.btn-group-vertical > .btn {
  position: relative;
  float: left;
}
.btn-group > .btn:hover,
.btn-group-vertical > .btn:hover,
.btn-group > .btn:focus,
.btn-group-vertical > .btn:focus,
.btn-group > .btn:active,
.btn-group-vertical > .btn:active,
.btn-group > .btn.active,
.btn-group-vertical > .btn.active {
  z-index: 2;
}
.btn-group .btn + .btn,
.btn-group .btn + .btn-group,
.btn-group .btn-group + .btn,
.btn-group .btn-group + .btn-group {
  margin-left: -1px;
}
.btn-toolbar {
  margin-left: -5px;
}
.btn-toolbar .btn,
.btn-toolbar .btn-group,
.btn-toolbar .input-group {
  float: left;
}
.btn-toolbar > .btn,
.btn-toolbar > .btn-group,
.btn-toolbar > .input-group {
  margin-left: 5px;
}
.btn-group > .btn:not(:first-child):not(:last-child):not(.dropdown-toggle) {
  border-radius: 0;
}
.btn-group > .btn:first-child {
  margin-left: 0;
}
.btn-group > .btn:first-child:not(:last-child):not(.dropdown-toggle) {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn:last-child:not(:first-child),
.btn-group > .dropdown-toggle:not(:first-child) {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group > .btn-group {
  float: left;
}
.btn-group > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group .dropdown-toggle:active,
.btn-group.open .dropdown-toggle {
  outline: 0;
}
.btn-group > .btn + .dropdown-toggle {
  padding-left: 8px;
  padding-right: 8px;
}
.btn-group > .btn-lg + .dropdown-toggle {
  padding-left: 12px;
  padding-right: 12px;
}
.btn-group.open .dropdown-toggle {
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn-group.open .dropdown-toggle.btn-link {
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn .caret {
  margin-left: 0;
}
.btn-lg .caret {
  border-width: 5px 5px 0;
  border-bottom-width: 0;
}
.dropup .btn-lg .caret {
  border-width: 0 5px 5px;
}
.btn-group-vertical > .btn,
.btn-group-vertical > .btn-group,
.btn-group-vertical > .btn-group > .btn {
  display: block;
  float: none;
  width: 100%;
  max-width: 100%;
}
.btn-group-vertical > .btn-group > .btn {
  float: none;
}
.btn-group-vertical > .btn + .btn,
.btn-group-vertical > .btn + .btn-group,
.btn-group-vertical > .btn-group + .btn,
.btn-group-vertical > .btn-group + .btn-group {
  margin-top: -1px;
  margin-left: 0;
}
.btn-group-vertical > .btn:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.btn-group-vertical > .btn:first-child:not(:last-child) {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn:last-child:not(:first-child) {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
.btn-group-vertical > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.btn-group-justified {
  display: table;
  width: 100%;
  table-layout: fixed;
  border-collapse: separate;
}
.btn-group-justified > .btn,
.btn-group-justified > .btn-group {
  float: none;
  display: table-cell;
  width: 1%;
}
.btn-group-justified > .btn-group .btn {
  width: 100%;
}
.btn-group-justified > .btn-group .dropdown-menu {
  left: auto;
}
[data-toggle="buttons"] > .btn input[type="radio"],
[data-toggle="buttons"] > .btn-group > .btn input[type="radio"],
[data-toggle="buttons"] > .btn input[type="checkbox"],
[data-toggle="buttons"] > .btn-group > .btn input[type="checkbox"] {
  position: absolute;
  clip: rect(0, 0, 0, 0);
  pointer-events: none;
}
.input-group {
  position: relative;
  display: table;
  border-collapse: separate;
}
.input-group[class*="col-"] {
  float: none;
  padding-left: 0;
  padding-right: 0;
}
.input-group .form-control {
  position: relative;
  z-index: 2;
  float: left;
  width: 100%;
  margin-bottom: 0;
}
.input-group .form-control:focus {
  z-index: 3;
}
.input-group-lg > .form-control,
.input-group-lg > .input-group-addon,
.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-group-lg > .form-control,
select.input-group-lg > .input-group-addon,
select.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  line-height: 45px;
}
textarea.input-group-lg > .form-control,
textarea.input-group-lg > .input-group-addon,
textarea.input-group-lg > .input-group-btn > .btn,
select[multiple].input-group-lg > .form-control,
select[multiple].input-group-lg > .input-group-addon,
select[multiple].input-group-lg > .input-group-btn > .btn {
  height: auto;
}
.input-group-sm > .form-control,
.input-group-sm > .input-group-addon,
.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-group-sm > .form-control,
select.input-group-sm > .input-group-addon,
select.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  line-height: 30px;
}
textarea.input-group-sm > .form-control,
textarea.input-group-sm > .input-group-addon,
textarea.input-group-sm > .input-group-btn > .btn,
select[multiple].input-group-sm > .form-control,
select[multiple].input-group-sm > .input-group-addon,
select[multiple].input-group-sm > .input-group-btn > .btn {
  height: auto;
}
.input-group-addon,
.input-group-btn,
.input-group .form-control {
  display: table-cell;
}
.input-group-addon:not(:first-child):not(:last-child),
.input-group-btn:not(:first-child):not(:last-child),
.input-group .form-control:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.input-group-addon,
.input-group-btn {
  width: 1%;
  white-space: nowrap;
  vertical-align: middle;
}
.input-group-addon {
  padding: 6px 12px;
  font-size: 13px;
  font-weight: normal;
  line-height: 1;
  color: #555555;
  text-align: center;
  background-color: #eeeeee;
  border: 1px solid #ccc;
  border-radius: 2px;
}
.input-group-addon.input-sm {
  padding: 5px 10px;
  font-size: 12px;
  border-radius: 1px;
}
.input-group-addon.input-lg {
  padding: 10px 16px;
  font-size: 17px;
  border-radius: 3px;
}
.input-group-addon input[type="radio"],
.input-group-addon input[type="checkbox"] {
  margin-top: 0;
}
.input-group .form-control:first-child,
.input-group-addon:first-child,
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group > .btn,
.input-group-btn:first-child > .dropdown-toggle,
.input-group-btn:last-child > .btn:not(:last-child):not(.dropdown-toggle),
.input-group-btn:last-child > .btn-group:not(:last-child) > .btn {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.input-group-addon:first-child {
  border-right: 0;
}
.input-group .form-control:last-child,
.input-group-addon:last-child,
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group > .btn,
.input-group-btn:last-child > .dropdown-toggle,
.input-group-btn:first-child > .btn:not(:first-child),
.input-group-btn:first-child > .btn-group:not(:first-child) > .btn {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.input-group-addon:last-child {
  border-left: 0;
}
.input-group-btn {
  position: relative;
  font-size: 0;
  white-space: nowrap;
}
.input-group-btn > .btn {
  position: relative;
}
.input-group-btn > .btn + .btn {
  margin-left: -1px;
}
.input-group-btn > .btn:hover,
.input-group-btn > .btn:focus,
.input-group-btn > .btn:active {
  z-index: 2;
}
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group {
  margin-right: -1px;
}
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group {
  z-index: 2;
  margin-left: -1px;
}
.nav {
  margin-bottom: 0;
  padding-left: 0;
  list-style: none;
}
.nav > li {
  position: relative;
  display: block;
}
.nav > li > a {
  position: relative;
  display: block;
  padding: 10px 15px;
}
.nav > li > a:hover,
.nav > li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.nav > li.disabled > a {
  color: #777777;
}
.nav > li.disabled > a:hover,
.nav > li.disabled > a:focus {
  color: #777777;
  text-decoration: none;
  background-color: transparent;
  cursor: not-allowed;
}
.nav .open > a,
.nav .open > a:hover,
.nav .open > a:focus {
  background-color: #eeeeee;
  border-color: #337ab7;
}
.nav .nav-divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.nav > li > a > img {
  max-width: none;
}
.nav-tabs {
  border-bottom: 1px solid #ddd;
}
.nav-tabs > li {
  float: left;
  margin-bottom: -1px;
}
.nav-tabs > li > a {
  margin-right: 2px;
  line-height: 1.42857143;
  border: 1px solid transparent;
  border-radius: 2px 2px 0 0;
}
.nav-tabs > li > a:hover {
  border-color: #eeeeee #eeeeee #ddd;
}
.nav-tabs > li.active > a,
.nav-tabs > li.active > a:hover,
.nav-tabs > li.active > a:focus {
  color: #555555;
  background-color: #fff;
  border: 1px solid #ddd;
  border-bottom-color: transparent;
  cursor: default;
}
.nav-tabs.nav-justified {
  width: 100%;
  border-bottom: 0;
}
.nav-tabs.nav-justified > li {
  float: none;
}
.nav-tabs.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-tabs.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-tabs.nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs.nav-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs.nav-justified > .active > a,
.nav-tabs.nav-justified > .active > a:hover,
.nav-tabs.nav-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs.nav-justified > .active > a,
  .nav-tabs.nav-justified > .active > a:hover,
  .nav-tabs.nav-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.nav-pills > li {
  float: left;
}
.nav-pills > li > a {
  border-radius: 2px;
}
.nav-pills > li + li {
  margin-left: 2px;
}
.nav-pills > li.active > a,
.nav-pills > li.active > a:hover,
.nav-pills > li.active > a:focus {
  color: #fff;
  background-color: #337ab7;
}
.nav-stacked > li {
  float: none;
}
.nav-stacked > li + li {
  margin-top: 2px;
  margin-left: 0;
}
.nav-justified {
  width: 100%;
}
.nav-justified > li {
  float: none;
}
.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs-justified {
  border-bottom: 0;
}
.nav-tabs-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs-justified > .active > a,
.nav-tabs-justified > .active > a:hover,
.nav-tabs-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs-justified > .active > a,
  .nav-tabs-justified > .active > a:hover,
  .nav-tabs-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.tab-content > .tab-pane {
  display: none;
}
.tab-content > .active {
  display: block;
}
.nav-tabs .dropdown-menu {
  margin-top: -1px;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar {
  position: relative;
  min-height: 30px;
  margin-bottom: 18px;
  border: 1px solid transparent;
}
@media (min-width: 541px) {
  .navbar {
    border-radius: 2px;
  }
}
@media (min-width: 541px) {
  .navbar-header {
    float: left;
  }
}
.navbar-collapse {
  overflow-x: visible;
  padding-right: 0px;
  padding-left: 0px;
  border-top: 1px solid transparent;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1);
  -webkit-overflow-scrolling: touch;
}
.navbar-collapse.in {
  overflow-y: auto;
}
@media (min-width: 541px) {
  .navbar-collapse {
    width: auto;
    border-top: 0;
    box-shadow: none;
  }
  .navbar-collapse.collapse {
    display: block !important;
    height: auto !important;
    padding-bottom: 0;
    overflow: visible !important;
  }
  .navbar-collapse.in {
    overflow-y: visible;
  }
  .navbar-fixed-top .navbar-collapse,
  .navbar-static-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    padding-left: 0;
    padding-right: 0;
  }
}
.navbar-fixed-top .navbar-collapse,
.navbar-fixed-bottom .navbar-collapse {
  max-height: 340px;
}
@media (max-device-width: 540px) and (orientation: landscape) {
  .navbar-fixed-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    max-height: 200px;
  }
}
.container > .navbar-header,
.container-fluid > .navbar-header,
.container > .navbar-collapse,
.container-fluid > .navbar-collapse {
  margin-right: 0px;
  margin-left: 0px;
}
@media (min-width: 541px) {
  .container > .navbar-header,
  .container-fluid > .navbar-header,
  .container > .navbar-collapse,
  .container-fluid > .navbar-collapse {
    margin-right: 0;
    margin-left: 0;
  }
}
.navbar-static-top {
  z-index: 1000;
  border-width: 0 0 1px;
}
@media (min-width: 541px) {
  .navbar-static-top {
    border-radius: 0;
  }
}
.navbar-fixed-top,
.navbar-fixed-bottom {
  position: fixed;
  right: 0;
  left: 0;
  z-index: 1030;
}
@media (min-width: 541px) {
  .navbar-fixed-top,
  .navbar-fixed-bottom {
    border-radius: 0;
  }
}
.navbar-fixed-top {
  top: 0;
  border-width: 0 0 1px;
}
.navbar-fixed-bottom {
  bottom: 0;
  margin-bottom: 0;
  border-width: 1px 0 0;
}
.navbar-brand {
  float: left;
  padding: 6px 0px;
  font-size: 17px;
  line-height: 18px;
  height: 30px;
}
.navbar-brand:hover,
.navbar-brand:focus {
  text-decoration: none;
}
.navbar-brand > img {
  display: block;
}
@media (min-width: 541px) {
  .navbar > .container .navbar-brand,
  .navbar > .container-fluid .navbar-brand {
    margin-left: 0px;
  }
}
.navbar-toggle {
  position: relative;
  float: right;
  margin-right: 0px;
  padding: 9px 10px;
  margin-top: -2px;
  margin-bottom: -2px;
  background-color: transparent;
  background-image: none;
  border: 1px solid transparent;
  border-radius: 2px;
}
.navbar-toggle:focus {
  outline: 0;
}
.navbar-toggle .icon-bar {
  display: block;
  width: 22px;
  height: 2px;
  border-radius: 1px;
}
.navbar-toggle .icon-bar + .icon-bar {
  margin-top: 4px;
}
@media (min-width: 541px) {
  .navbar-toggle {
    display: none;
  }
}
.navbar-nav {
  margin: 3px 0px;
}
.navbar-nav > li > a {
  padding-top: 10px;
  padding-bottom: 10px;
  line-height: 18px;
}
@media (max-width: 540px) {
  .navbar-nav .open .dropdown-menu {
    position: static;
    float: none;
    width: auto;
    margin-top: 0;
    background-color: transparent;
    border: 0;
    box-shadow: none;
  }
  .navbar-nav .open .dropdown-menu > li > a,
  .navbar-nav .open .dropdown-menu .dropdown-header {
    padding: 5px 15px 5px 25px;
  }
  .navbar-nav .open .dropdown-menu > li > a {
    line-height: 18px;
  }
  .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-nav .open .dropdown-menu > li > a:focus {
    background-image: none;
  }
}
@media (min-width: 541px) {
  .navbar-nav {
    float: left;
    margin: 0;
  }
  .navbar-nav > li {
    float: left;
  }
  .navbar-nav > li > a {
    padding-top: 6px;
    padding-bottom: 6px;
  }
}
.navbar-form {
  margin-left: 0px;
  margin-right: 0px;
  padding: 10px 0px;
  border-top: 1px solid transparent;
  border-bottom: 1px solid transparent;
  -webkit-box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  margin-top: -1px;
  margin-bottom: -1px;
}
@media (min-width: 768px) {
  .navbar-form .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .navbar-form .form-control-static {
    display: inline-block;
  }
  .navbar-form .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .navbar-form .input-group .input-group-addon,
  .navbar-form .input-group .input-group-btn,
  .navbar-form .input-group .form-control {
    width: auto;
  }
  .navbar-form .input-group > .form-control {
    width: 100%;
  }
  .navbar-form .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio,
  .navbar-form .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio label,
  .navbar-form .checkbox label {
    padding-left: 0;
  }
  .navbar-form .radio input[type="radio"],
  .navbar-form .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .navbar-form .has-feedback .form-control-feedback {
    top: 0;
  }
}
@media (max-width: 540px) {
  .navbar-form .form-group {
    margin-bottom: 5px;
  }
  .navbar-form .form-group:last-child {
    margin-bottom: 0;
  }
}
@media (min-width: 541px) {
  .navbar-form {
    width: auto;
    border: 0;
    margin-left: 0;
    margin-right: 0;
    padding-top: 0;
    padding-bottom: 0;
    -webkit-box-shadow: none;
    box-shadow: none;
  }
}
.navbar-nav > li > .dropdown-menu {
  margin-top: 0;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar-fixed-bottom .navbar-nav > li > .dropdown-menu {
  margin-bottom: 0;
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.navbar-btn {
  margin-top: -1px;
  margin-bottom: -1px;
}
.navbar-btn.btn-sm {
  margin-top: 0px;
  margin-bottom: 0px;
}
.navbar-btn.btn-xs {
  margin-top: 4px;
  margin-bottom: 4px;
}
.navbar-text {
  margin-top: 6px;
  margin-bottom: 6px;
}
@media (min-width: 541px) {
  .navbar-text {
    float: left;
    margin-left: 0px;
    margin-right: 0px;
  }
}
@media (min-width: 541px) {
  .navbar-left {
    float: left !important;
    float: left;
  }
  .navbar-right {
    float: right !important;
    float: right;
    margin-right: 0px;
  }
  .navbar-right ~ .navbar-right {
    margin-right: 0;
  }
}
.navbar-default {
  background-color: #f8f8f8;
  border-color: #e7e7e7;
}
.navbar-default .navbar-brand {
  color: #777;
}
.navbar-default .navbar-brand:hover,
.navbar-default .navbar-brand:focus {
  color: #5e5e5e;
  background-color: transparent;
}
.navbar-default .navbar-text {
  color: #777;
}
.navbar-default .navbar-nav > li > a {
  color: #777;
}
.navbar-default .navbar-nav > li > a:hover,
.navbar-default .navbar-nav > li > a:focus {
  color: #333;
  background-color: transparent;
}
.navbar-default .navbar-nav > .active > a,
.navbar-default .navbar-nav > .active > a:hover,
.navbar-default .navbar-nav > .active > a:focus {
  color: #555;
  background-color: #e7e7e7;
}
.navbar-default .navbar-nav > .disabled > a,
.navbar-default .navbar-nav > .disabled > a:hover,
.navbar-default .navbar-nav > .disabled > a:focus {
  color: #ccc;
  background-color: transparent;
}
.navbar-default .navbar-toggle {
  border-color: #ddd;
}
.navbar-default .navbar-toggle:hover,
.navbar-default .navbar-toggle:focus {
  background-color: #ddd;
}
.navbar-default .navbar-toggle .icon-bar {
  background-color: #888;
}
.navbar-default .navbar-collapse,
.navbar-default .navbar-form {
  border-color: #e7e7e7;
}
.navbar-default .navbar-nav > .open > a,
.navbar-default .navbar-nav > .open > a:hover,
.navbar-default .navbar-nav > .open > a:focus {
  background-color: #e7e7e7;
  color: #555;
}
@media (max-width: 540px) {
  .navbar-default .navbar-nav .open .dropdown-menu > li > a {
    color: #777;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #333;
    background-color: transparent;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #555;
    background-color: #e7e7e7;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #ccc;
    background-color: transparent;
  }
}
.navbar-default .navbar-link {
  color: #777;
}
.navbar-default .navbar-link:hover {
  color: #333;
}
.navbar-default .btn-link {
  color: #777;
}
.navbar-default .btn-link:hover,
.navbar-default .btn-link:focus {
  color: #333;
}
.navbar-default .btn-link[disabled]:hover,
fieldset[disabled] .navbar-default .btn-link:hover,
.navbar-default .btn-link[disabled]:focus,
fieldset[disabled] .navbar-default .btn-link:focus {
  color: #ccc;
}
.navbar-inverse {
  background-color: #222;
  border-color: #080808;
}
.navbar-inverse .navbar-brand {
  color: #9d9d9d;
}
.navbar-inverse .navbar-brand:hover,
.navbar-inverse .navbar-brand:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-text {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a:hover,
.navbar-inverse .navbar-nav > li > a:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-nav > .active > a,
.navbar-inverse .navbar-nav > .active > a:hover,
.navbar-inverse .navbar-nav > .active > a:focus {
  color: #fff;
  background-color: #080808;
}
.navbar-inverse .navbar-nav > .disabled > a,
.navbar-inverse .navbar-nav > .disabled > a:hover,
.navbar-inverse .navbar-nav > .disabled > a:focus {
  color: #444;
  background-color: transparent;
}
.navbar-inverse .navbar-toggle {
  border-color: #333;
}
.navbar-inverse .navbar-toggle:hover,
.navbar-inverse .navbar-toggle:focus {
  background-color: #333;
}
.navbar-inverse .navbar-toggle .icon-bar {
  background-color: #fff;
}
.navbar-inverse .navbar-collapse,
.navbar-inverse .navbar-form {
  border-color: #101010;
}
.navbar-inverse .navbar-nav > .open > a,
.navbar-inverse .navbar-nav > .open > a:hover,
.navbar-inverse .navbar-nav > .open > a:focus {
  background-color: #080808;
  color: #fff;
}
@media (max-width: 540px) {
  .navbar-inverse .navbar-nav .open .dropdown-menu > .dropdown-header {
    border-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu .divider {
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a {
    color: #9d9d9d;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #fff;
    background-color: transparent;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #fff;
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #444;
    background-color: transparent;
  }
}
.navbar-inverse .navbar-link {
  color: #9d9d9d;
}
.navbar-inverse .navbar-link:hover {
  color: #fff;
}
.navbar-inverse .btn-link {
  color: #9d9d9d;
}
.navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link:focus {
  color: #fff;
}
.navbar-inverse .btn-link[disabled]:hover,
fieldset[disabled] .navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link[disabled]:focus,
fieldset[disabled] .navbar-inverse .btn-link:focus {
  color: #444;
}
.breadcrumb {
  padding: 8px 15px;
  margin-bottom: 18px;
  list-style: none;
  background-color: #f5f5f5;
  border-radius: 2px;
}
.breadcrumb > li {
  display: inline-block;
}
.breadcrumb > li + li:before {
  content: "/\00a0";
  padding: 0 5px;
  color: #5e5e5e;
}
.breadcrumb > .active {
  color: #777777;
}
.pagination {
  display: inline-block;
  padding-left: 0;
  margin: 18px 0;
  border-radius: 2px;
}
.pagination > li {
  display: inline;
}
.pagination > li > a,
.pagination > li > span {
  position: relative;
  float: left;
  padding: 6px 12px;
  line-height: 1.42857143;
  text-decoration: none;
  color: #337ab7;
  background-color: #fff;
  border: 1px solid #ddd;
  margin-left: -1px;
}
.pagination > li:first-child > a,
.pagination > li:first-child > span {
  margin-left: 0;
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.pagination > li:last-child > a,
.pagination > li:last-child > span {
  border-bottom-right-radius: 2px;
  border-top-right-radius: 2px;
}
.pagination > li > a:hover,
.pagination > li > span:hover,
.pagination > li > a:focus,
.pagination > li > span:focus {
  z-index: 2;
  color: #23527c;
  background-color: #eeeeee;
  border-color: #ddd;
}
.pagination > .active > a,
.pagination > .active > span,
.pagination > .active > a:hover,
.pagination > .active > span:hover,
.pagination > .active > a:focus,
.pagination > .active > span:focus {
  z-index: 3;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
  cursor: default;
}
.pagination > .disabled > span,
.pagination > .disabled > span:hover,
.pagination > .disabled > span:focus,
.pagination > .disabled > a,
.pagination > .disabled > a:hover,
.pagination > .disabled > a:focus {
  color: #777777;
  background-color: #fff;
  border-color: #ddd;
  cursor: not-allowed;
}
.pagination-lg > li > a,
.pagination-lg > li > span {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.pagination-lg > li:first-child > a,
.pagination-lg > li:first-child > span {
  border-bottom-left-radius: 3px;
  border-top-left-radius: 3px;
}
.pagination-lg > li:last-child > a,
.pagination-lg > li:last-child > span {
  border-bottom-right-radius: 3px;
  border-top-right-radius: 3px;
}
.pagination-sm > li > a,
.pagination-sm > li > span {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.pagination-sm > li:first-child > a,
.pagination-sm > li:first-child > span {
  border-bottom-left-radius: 1px;
  border-top-left-radius: 1px;
}
.pagination-sm > li:last-child > a,
.pagination-sm > li:last-child > span {
  border-bottom-right-radius: 1px;
  border-top-right-radius: 1px;
}
.pager {
  padding-left: 0;
  margin: 18px 0;
  list-style: none;
  text-align: center;
}
.pager li {
  display: inline;
}
.pager li > a,
.pager li > span {
  display: inline-block;
  padding: 5px 14px;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 15px;
}
.pager li > a:hover,
.pager li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.pager .next > a,
.pager .next > span {
  float: right;
}
.pager .previous > a,
.pager .previous > span {
  float: left;
}
.pager .disabled > a,
.pager .disabled > a:hover,
.pager .disabled > a:focus,
.pager .disabled > span {
  color: #777777;
  background-color: #fff;
  cursor: not-allowed;
}
.label {
  display: inline;
  padding: .2em .6em .3em;
  font-size: 75%;
  font-weight: bold;
  line-height: 1;
  color: #fff;
  text-align: center;
  white-space: nowrap;
  vertical-align: baseline;
  border-radius: .25em;
}
a.label:hover,
a.label:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.label:empty {
  display: none;
}
.btn .label {
  position: relative;
  top: -1px;
}
.label-default {
  background-color: #777777;
}
.label-default[href]:hover,
.label-default[href]:focus {
  background-color: #5e5e5e;
}
.label-primary {
  background-color: #337ab7;
}
.label-primary[href]:hover,
.label-primary[href]:focus {
  background-color: #286090;
}
.label-success {
  background-color: #5cb85c;
}
.label-success[href]:hover,
.label-success[href]:focus {
  background-color: #449d44;
}
.label-info {
  background-color: #5bc0de;
}
.label-info[href]:hover,
.label-info[href]:focus {
  background-color: #31b0d5;
}
.label-warning {
  background-color: #f0ad4e;
}
.label-warning[href]:hover,
.label-warning[href]:focus {
  background-color: #ec971f;
}
.label-danger {
  background-color: #d9534f;
}
.label-danger[href]:hover,
.label-danger[href]:focus {
  background-color: #c9302c;
}
.badge {
  display: inline-block;
  min-width: 10px;
  padding: 3px 7px;
  font-size: 12px;
  font-weight: bold;
  color: #fff;
  line-height: 1;
  vertical-align: middle;
  white-space: nowrap;
  text-align: center;
  background-color: #777777;
  border-radius: 10px;
}
.badge:empty {
  display: none;
}
.btn .badge {
  position: relative;
  top: -1px;
}
.btn-xs .badge,
.btn-group-xs > .btn .badge {
  top: 0;
  padding: 1px 5px;
}
a.badge:hover,
a.badge:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.list-group-item.active > .badge,
.nav-pills > .active > a > .badge {
  color: #337ab7;
  background-color: #fff;
}
.list-group-item > .badge {
  float: right;
}
.list-group-item > .badge + .badge {
  margin-right: 5px;
}
.nav-pills > li > a > .badge {
  margin-left: 3px;
}
.jumbotron {
  padding-top: 30px;
  padding-bottom: 30px;
  margin-bottom: 30px;
  color: inherit;
  background-color: #eeeeee;
}
.jumbotron h1,
.jumbotron .h1 {
  color: inherit;
}
.jumbotron p {
  margin-bottom: 15px;
  font-size: 20px;
  font-weight: 200;
}
.jumbotron > hr {
  border-top-color: #d5d5d5;
}
.container .jumbotron,
.container-fluid .jumbotron {
  border-radius: 3px;
  padding-left: 0px;
  padding-right: 0px;
}
.jumbotron .container {
  max-width: 100%;
}
@media screen and (min-width: 768px) {
  .jumbotron {
    padding-top: 48px;
    padding-bottom: 48px;
  }
  .container .jumbotron,
  .container-fluid .jumbotron {
    padding-left: 60px;
    padding-right: 60px;
  }
  .jumbotron h1,
  .jumbotron .h1 {
    font-size: 59px;
  }
}
.thumbnail {
  display: block;
  padding: 4px;
  margin-bottom: 18px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: border 0.2s ease-in-out;
  -o-transition: border 0.2s ease-in-out;
  transition: border 0.2s ease-in-out;
}
.thumbnail > img,
.thumbnail a > img {
  margin-left: auto;
  margin-right: auto;
}
a.thumbnail:hover,
a.thumbnail:focus,
a.thumbnail.active {
  border-color: #337ab7;
}
.thumbnail .caption {
  padding: 9px;
  color: #000;
}
.alert {
  padding: 15px;
  margin-bottom: 18px;
  border: 1px solid transparent;
  border-radius: 2px;
}
.alert h4 {
  margin-top: 0;
  color: inherit;
}
.alert .alert-link {
  font-weight: bold;
}
.alert > p,
.alert > ul {
  margin-bottom: 0;
}
.alert > p + p {
  margin-top: 5px;
}
.alert-dismissable,
.alert-dismissible {
  padding-right: 35px;
}
.alert-dismissable .close,
.alert-dismissible .close {
  position: relative;
  top: -2px;
  right: -21px;
  color: inherit;
}
.alert-success {
  background-color: #dff0d8;
  border-color: #d6e9c6;
  color: #3c763d;
}
.alert-success hr {
  border-top-color: #c9e2b3;
}
.alert-success .alert-link {
  color: #2b542c;
}
.alert-info {
  background-color: #d9edf7;
  border-color: #bce8f1;
  color: #31708f;
}
.alert-info hr {
  border-top-color: #a6e1ec;
}
.alert-info .alert-link {
  color: #245269;
}
.alert-warning {
  background-color: #fcf8e3;
  border-color: #faebcc;
  color: #8a6d3b;
}
.alert-warning hr {
  border-top-color: #f7e1b5;
}
.alert-warning .alert-link {
  color: #66512c;
}
.alert-danger {
  background-color: #f2dede;
  border-color: #ebccd1;
  color: #a94442;
}
.alert-danger hr {
  border-top-color: #e4b9c0;
}
.alert-danger .alert-link {
  color: #843534;
}
@-webkit-keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
@keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
.progress {
  overflow: hidden;
  height: 18px;
  margin-bottom: 18px;
  background-color: #f5f5f5;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
  box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
}
.progress-bar {
  float: left;
  width: 0%;
  height: 100%;
  font-size: 12px;
  line-height: 18px;
  color: #fff;
  text-align: center;
  background-color: #337ab7;
  -webkit-box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  -webkit-transition: width 0.6s ease;
  -o-transition: width 0.6s ease;
  transition: width 0.6s ease;
}
.progress-striped .progress-bar,
.progress-bar-striped {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-size: 40px 40px;
}
.progress.active .progress-bar,
.progress-bar.active {
  -webkit-animation: progress-bar-stripes 2s linear infinite;
  -o-animation: progress-bar-stripes 2s linear infinite;
  animation: progress-bar-stripes 2s linear infinite;
}
.progress-bar-success {
  background-color: #5cb85c;
}
.progress-striped .progress-bar-success {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-info {
  background-color: #5bc0de;
}
.progress-striped .progress-bar-info {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-warning {
  background-color: #f0ad4e;
}
.progress-striped .progress-bar-warning {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-danger {
  background-color: #d9534f;
}
.progress-striped .progress-bar-danger {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.media {
  margin-top: 15px;
}
.media:first-child {
  margin-top: 0;
}
.media,
.media-body {
  zoom: 1;
  overflow: hidden;
}
.media-body {
  width: 10000px;
}
.media-object {
  display: block;
}
.media-object.img-thumbnail {
  max-width: none;
}
.media-right,
.media > .pull-right {
  padding-left: 10px;
}
.media-left,
.media > .pull-left {
  padding-right: 10px;
}
.media-left,
.media-right,
.media-body {
  display: table-cell;
  vertical-align: top;
}
.media-middle {
  vertical-align: middle;
}
.media-bottom {
  vertical-align: bottom;
}
.media-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.media-list {
  padding-left: 0;
  list-style: none;
}
.list-group {
  margin-bottom: 20px;
  padding-left: 0;
}
.list-group-item {
  position: relative;
  display: block;
  padding: 10px 15px;
  margin-bottom: -1px;
  background-color: #fff;
  border: 1px solid #ddd;
}
.list-group-item:first-child {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
}
.list-group-item:last-child {
  margin-bottom: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
a.list-group-item,
button.list-group-item {
  color: #555;
}
a.list-group-item .list-group-item-heading,
button.list-group-item .list-group-item-heading {
  color: #333;
}
a.list-group-item:hover,
button.list-group-item:hover,
a.list-group-item:focus,
button.list-group-item:focus {
  text-decoration: none;
  color: #555;
  background-color: #f5f5f5;
}
button.list-group-item {
  width: 100%;
  text-align: left;
}
.list-group-item.disabled,
.list-group-item.disabled:hover,
.list-group-item.disabled:focus {
  background-color: #eeeeee;
  color: #777777;
  cursor: not-allowed;
}
.list-group-item.disabled .list-group-item-heading,
.list-group-item.disabled:hover .list-group-item-heading,
.list-group-item.disabled:focus .list-group-item-heading {
  color: inherit;
}
.list-group-item.disabled .list-group-item-text,
.list-group-item.disabled:hover .list-group-item-text,
.list-group-item.disabled:focus .list-group-item-text {
  color: #777777;
}
.list-group-item.active,
.list-group-item.active:hover,
.list-group-item.active:focus {
  z-index: 2;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.list-group-item.active .list-group-item-heading,
.list-group-item.active:hover .list-group-item-heading,
.list-group-item.active:focus .list-group-item-heading,
.list-group-item.active .list-group-item-heading > small,
.list-group-item.active:hover .list-group-item-heading > small,
.list-group-item.active:focus .list-group-item-heading > small,
.list-group-item.active .list-group-item-heading > .small,
.list-group-item.active:hover .list-group-item-heading > .small,
.list-group-item.active:focus .list-group-item-heading > .small {
  color: inherit;
}
.list-group-item.active .list-group-item-text,
.list-group-item.active:hover .list-group-item-text,
.list-group-item.active:focus .list-group-item-text {
  color: #c7ddef;
}
.list-group-item-success {
  color: #3c763d;
  background-color: #dff0d8;
}
a.list-group-item-success,
button.list-group-item-success {
  color: #3c763d;
}
a.list-group-item-success .list-group-item-heading,
button.list-group-item-success .list-group-item-heading {
  color: inherit;
}
a.list-group-item-success:hover,
button.list-group-item-success:hover,
a.list-group-item-success:focus,
button.list-group-item-success:focus {
  color: #3c763d;
  background-color: #d0e9c6;
}
a.list-group-item-success.active,
button.list-group-item-success.active,
a.list-group-item-success.active:hover,
button.list-group-item-success.active:hover,
a.list-group-item-success.active:focus,
button.list-group-item-success.active:focus {
  color: #fff;
  background-color: #3c763d;
  border-color: #3c763d;
}
.list-group-item-info {
  color: #31708f;
  background-color: #d9edf7;
}
a.list-group-item-info,
button.list-group-item-info {
  color: #31708f;
}
a.list-group-item-info .list-group-item-heading,
button.list-group-item-info .list-group-item-heading {
  color: inherit;
}
a.list-group-item-info:hover,
button.list-group-item-info:hover,
a.list-group-item-info:focus,
button.list-group-item-info:focus {
  color: #31708f;
  background-color: #c4e3f3;
}
a.list-group-item-info.active,
button.list-group-item-info.active,
a.list-group-item-info.active:hover,
button.list-group-item-info.active:hover,
a.list-group-item-info.active:focus,
button.list-group-item-info.active:focus {
  color: #fff;
  background-color: #31708f;
  border-color: #31708f;
}
.list-group-item-warning {
  color: #8a6d3b;
  background-color: #fcf8e3;
}
a.list-group-item-warning,
button.list-group-item-warning {
  color: #8a6d3b;
}
a.list-group-item-warning .list-group-item-heading,
button.list-group-item-warning .list-group-item-heading {
  color: inherit;
}
a.list-group-item-warning:hover,
button.list-group-item-warning:hover,
a.list-group-item-warning:focus,
button.list-group-item-warning:focus {
  color: #8a6d3b;
  background-color: #faf2cc;
}
a.list-group-item-warning.active,
button.list-group-item-warning.active,
a.list-group-item-warning.active:hover,
button.list-group-item-warning.active:hover,
a.list-group-item-warning.active:focus,
button.list-group-item-warning.active:focus {
  color: #fff;
  background-color: #8a6d3b;
  border-color: #8a6d3b;
}
.list-group-item-danger {
  color: #a94442;
  background-color: #f2dede;
}
a.list-group-item-danger,
button.list-group-item-danger {
  color: #a94442;
}
a.list-group-item-danger .list-group-item-heading,
button.list-group-item-danger .list-group-item-heading {
  color: inherit;
}
a.list-group-item-danger:hover,
button.list-group-item-danger:hover,
a.list-group-item-danger:focus,
button.list-group-item-danger:focus {
  color: #a94442;
  background-color: #ebcccc;
}
a.list-group-item-danger.active,
button.list-group-item-danger.active,
a.list-group-item-danger.active:hover,
button.list-group-item-danger.active:hover,
a.list-group-item-danger.active:focus,
button.list-group-item-danger.active:focus {
  color: #fff;
  background-color: #a94442;
  border-color: #a94442;
}
.list-group-item-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.list-group-item-text {
  margin-bottom: 0;
  line-height: 1.3;
}
.panel {
  margin-bottom: 18px;
  background-color: #fff;
  border: 1px solid transparent;
  border-radius: 2px;
  -webkit-box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
}
.panel-body {
  padding: 15px;
}
.panel-heading {
  padding: 10px 15px;
  border-bottom: 1px solid transparent;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel-heading > .dropdown .dropdown-toggle {
  color: inherit;
}
.panel-title {
  margin-top: 0;
  margin-bottom: 0;
  font-size: 15px;
  color: inherit;
}
.panel-title > a,
.panel-title > small,
.panel-title > .small,
.panel-title > small > a,
.panel-title > .small > a {
  color: inherit;
}
.panel-footer {
  padding: 10px 15px;
  background-color: #f5f5f5;
  border-top: 1px solid #ddd;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .list-group,
.panel > .panel-collapse > .list-group {
  margin-bottom: 0;
}
.panel > .list-group .list-group-item,
.panel > .panel-collapse > .list-group .list-group-item {
  border-width: 1px 0;
  border-radius: 0;
}
.panel > .list-group:first-child .list-group-item:first-child,
.panel > .panel-collapse > .list-group:first-child .list-group-item:first-child {
  border-top: 0;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .list-group:last-child .list-group-item:last-child,
.panel > .panel-collapse > .list-group:last-child .list-group-item:last-child {
  border-bottom: 0;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .panel-heading + .panel-collapse > .list-group .list-group-item:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.panel-heading + .list-group .list-group-item:first-child {
  border-top-width: 0;
}
.list-group + .panel-footer {
  border-top-width: 0;
}
.panel > .table,
.panel > .table-responsive > .table,
.panel > .panel-collapse > .table {
  margin-bottom: 0;
}
.panel > .table caption,
.panel > .table-responsive > .table caption,
.panel > .panel-collapse > .table caption {
  padding-left: 15px;
  padding-right: 15px;
}
.panel > .table:first-child,
.panel > .table-responsive:first-child > .table:first-child {
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child {
  border-top-left-radius: 1px;
  border-top-right-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:first-child {
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:last-child {
  border-top-right-radius: 1px;
}
.panel > .table:last-child,
.panel > .table-responsive:last-child > .table:last-child {
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child {
  border-bottom-left-radius: 1px;
  border-bottom-right-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:first-child {
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:last-child {
  border-bottom-right-radius: 1px;
}
.panel > .panel-body + .table,
.panel > .panel-body + .table-responsive,
.panel > .table + .panel-body,
.panel > .table-responsive + .panel-body {
  border-top: 1px solid #ddd;
}
.panel > .table > tbody:first-child > tr:first-child th,
.panel > .table > tbody:first-child > tr:first-child td {
  border-top: 0;
}
.panel > .table-bordered,
.panel > .table-responsive > .table-bordered {
  border: 0;
}
.panel > .table-bordered > thead > tr > th:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:first-child,
.panel > .table-bordered > tbody > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:first-child,
.panel > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-bordered > thead > tr > td:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:first-child,
.panel > .table-bordered > tbody > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:first-child,
.panel > .table-bordered > tfoot > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:first-child {
  border-left: 0;
}
.panel > .table-bordered > thead > tr > th:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:last-child,
.panel > .table-bordered > tbody > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:last-child,
.panel > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-bordered > thead > tr > td:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:last-child,
.panel > .table-bordered > tbody > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:last-child,
.panel > .table-bordered > tfoot > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:last-child {
  border-right: 0;
}
.panel > .table-bordered > thead > tr:first-child > td,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > td,
.panel > .table-bordered > tbody > tr:first-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > td,
.panel > .table-bordered > thead > tr:first-child > th,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > th,
.panel > .table-bordered > tbody > tr:first-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > th {
  border-bottom: 0;
}
.panel > .table-bordered > tbody > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > td,
.panel > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-bordered > tbody > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > th,
.panel > .table-bordered > tfoot > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > th {
  border-bottom: 0;
}
.panel > .table-responsive {
  border: 0;
  margin-bottom: 0;
}
.panel-group {
  margin-bottom: 18px;
}
.panel-group .panel {
  margin-bottom: 0;
  border-radius: 2px;
}
.panel-group .panel + .panel {
  margin-top: 5px;
}
.panel-group .panel-heading {
  border-bottom: 0;
}
.panel-group .panel-heading + .panel-collapse > .panel-body,
.panel-group .panel-heading + .panel-collapse > .list-group {
  border-top: 1px solid #ddd;
}
.panel-group .panel-footer {
  border-top: 0;
}
.panel-group .panel-footer + .panel-collapse .panel-body {
  border-bottom: 1px solid #ddd;
}
.panel-default {
  border-color: #ddd;
}
.panel-default > .panel-heading {
  color: #333333;
  background-color: #f5f5f5;
  border-color: #ddd;
}
.panel-default > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ddd;
}
.panel-default > .panel-heading .badge {
  color: #f5f5f5;
  background-color: #333333;
}
.panel-default > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ddd;
}
.panel-primary {
  border-color: #337ab7;
}
.panel-primary > .panel-heading {
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.panel-primary > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #337ab7;
}
.panel-primary > .panel-heading .badge {
  color: #337ab7;
  background-color: #fff;
}
.panel-primary > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #337ab7;
}
.panel-success {
  border-color: #d6e9c6;
}
.panel-success > .panel-heading {
  color: #3c763d;
  background-color: #dff0d8;
  border-color: #d6e9c6;
}
.panel-success > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #d6e9c6;
}
.panel-success > .panel-heading .badge {
  color: #dff0d8;
  background-color: #3c763d;
}
.panel-success > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #d6e9c6;
}
.panel-info {
  border-color: #bce8f1;
}
.panel-info > .panel-heading {
  color: #31708f;
  background-color: #d9edf7;
  border-color: #bce8f1;
}
.panel-info > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #bce8f1;
}
.panel-info > .panel-heading .badge {
  color: #d9edf7;
  background-color: #31708f;
}
.panel-info > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #bce8f1;
}
.panel-warning {
  border-color: #faebcc;
}
.panel-warning > .panel-heading {
  color: #8a6d3b;
  background-color: #fcf8e3;
  border-color: #faebcc;
}
.panel-warning > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #faebcc;
}
.panel-warning > .panel-heading .badge {
  color: #fcf8e3;
  background-color: #8a6d3b;
}
.panel-warning > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #faebcc;
}
.panel-danger {
  border-color: #ebccd1;
}
.panel-danger > .panel-heading {
  color: #a94442;
  background-color: #f2dede;
  border-color: #ebccd1;
}
.panel-danger > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ebccd1;
}
.panel-danger > .panel-heading .badge {
  color: #f2dede;
  background-color: #a94442;
}
.panel-danger > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ebccd1;
}
.embed-responsive {
  position: relative;
  display: block;
  height: 0;
  padding: 0;
  overflow: hidden;
}
.embed-responsive .embed-responsive-item,
.embed-responsive iframe,
.embed-responsive embed,
.embed-responsive object,
.embed-responsive video {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  height: 100%;
  width: 100%;
  border: 0;
}
.embed-responsive-16by9 {
  padding-bottom: 56.25%;
}
.embed-responsive-4by3 {
  padding-bottom: 75%;
}
.well {
  min-height: 20px;
  padding: 19px;
  margin-bottom: 20px;
  background-color: #f5f5f5;
  border: 1px solid #e3e3e3;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
}
.well blockquote {
  border-color: #ddd;
  border-color: rgba(0, 0, 0, 0.15);
}
.well-lg {
  padding: 24px;
  border-radius: 3px;
}
.well-sm {
  padding: 9px;
  border-radius: 1px;
}
.close {
  float: right;
  font-size: 19.5px;
  font-weight: bold;
  line-height: 1;
  color: #000;
  text-shadow: 0 1px 0 #fff;
  opacity: 0.2;
  filter: alpha(opacity=20);
}
.close:hover,
.close:focus {
  color: #000;
  text-decoration: none;
  cursor: pointer;
  opacity: 0.5;
  filter: alpha(opacity=50);
}
button.close {
  padding: 0;
  cursor: pointer;
  background: transparent;
  border: 0;
  -webkit-appearance: none;
}
.modal-open {
  overflow: hidden;
}
.modal {
  display: none;
  overflow: hidden;
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1050;
  -webkit-overflow-scrolling: touch;
  outline: 0;
}
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, -25%);
  -ms-transform: translate(0, -25%);
  -o-transform: translate(0, -25%);
  transform: translate(0, -25%);
  -webkit-transition: -webkit-transform 0.3s ease-out;
  -moz-transition: -moz-transform 0.3s ease-out;
  -o-transition: -o-transform 0.3s ease-out;
  transition: transform 0.3s ease-out;
}
.modal.in .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
.modal-open .modal {
  overflow-x: hidden;
  overflow-y: auto;
}
.modal-dialog {
  position: relative;
  width: auto;
  margin: 10px;
}
.modal-content {
  position: relative;
  background-color: #fff;
  border: 1px solid #999;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  background-clip: padding-box;
  outline: 0;
}
.modal-backdrop {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1040;
  background-color: #000;
}
.modal-backdrop.fade {
  opacity: 0;
  filter: alpha(opacity=0);
}
.modal-backdrop.in {
  opacity: 0.5;
  filter: alpha(opacity=50);
}
.modal-header {
  padding: 15px;
  border-bottom: 1px solid #e5e5e5;
}
.modal-header .close {
  margin-top: -2px;
}
.modal-title {
  margin: 0;
  line-height: 1.42857143;
}
.modal-body {
  position: relative;
  padding: 15px;
}
.modal-footer {
  padding: 15px;
  text-align: right;
  border-top: 1px solid #e5e5e5;
}
.modal-footer .btn + .btn {
  margin-left: 5px;
  margin-bottom: 0;
}
.modal-footer .btn-group .btn + .btn {
  margin-left: -1px;
}
.modal-footer .btn-block + .btn-block {
  margin-left: 0;
}
.modal-scrollbar-measure {
  position: absolute;
  top: -9999px;
  width: 50px;
  height: 50px;
  overflow: scroll;
}
@media (min-width: 768px) {
  .modal-dialog {
    width: 600px;
    margin: 30px auto;
  }
  .modal-content {
    -webkit-box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
  }
  .modal-sm {
    width: 300px;
  }
}
@media (min-width: 992px) {
  .modal-lg {
    width: 900px;
  }
}
.tooltip {
  position: absolute;
  z-index: 1070;
  display: block;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 12px;
  opacity: 0;
  filter: alpha(opacity=0);
}
.tooltip.in {
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.tooltip.top {
  margin-top: -3px;
  padding: 5px 0;
}
.tooltip.right {
  margin-left: 3px;
  padding: 0 5px;
}
.tooltip.bottom {
  margin-top: 3px;
  padding: 5px 0;
}
.tooltip.left {
  margin-left: -3px;
  padding: 0 5px;
}
.tooltip-inner {
  max-width: 200px;
  padding: 3px 8px;
  color: #fff;
  text-align: center;
  background-color: #000;
  border-radius: 2px;
}
.tooltip-arrow {
  position: absolute;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.tooltip.top .tooltip-arrow {
  bottom: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-left .tooltip-arrow {
  bottom: 0;
  right: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-right .tooltip-arrow {
  bottom: 0;
  left: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.right .tooltip-arrow {
  top: 50%;
  left: 0;
  margin-top: -5px;
  border-width: 5px 5px 5px 0;
  border-right-color: #000;
}
.tooltip.left .tooltip-arrow {
  top: 50%;
  right: 0;
  margin-top: -5px;
  border-width: 5px 0 5px 5px;
  border-left-color: #000;
}
.tooltip.bottom .tooltip-arrow {
  top: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-left .tooltip-arrow {
  top: 0;
  right: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-right .tooltip-arrow {
  top: 0;
  left: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.popover {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1060;
  display: none;
  max-width: 276px;
  padding: 1px;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 13px;
  background-color: #fff;
  background-clip: padding-box;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
}
.popover.top {
  margin-top: -10px;
}
.popover.right {
  margin-left: 10px;
}
.popover.bottom {
  margin-top: 10px;
}
.popover.left {
  margin-left: -10px;
}
.popover-title {
  margin: 0;
  padding: 8px 14px;
  font-size: 13px;
  background-color: #f7f7f7;
  border-bottom: 1px solid #ebebeb;
  border-radius: 2px 2px 0 0;
}
.popover-content {
  padding: 9px 14px;
}
.popover > .arrow,
.popover > .arrow:after {
  position: absolute;
  display: block;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.popover > .arrow {
  border-width: 11px;
}
.popover > .arrow:after {
  border-width: 10px;
  content: "";
}
.popover.top > .arrow {
  left: 50%;
  margin-left: -11px;
  border-bottom-width: 0;
  border-top-color: #999999;
  border-top-color: rgba(0, 0, 0, 0.25);
  bottom: -11px;
}
.popover.top > .arrow:after {
  content: " ";
  bottom: 1px;
  margin-left: -10px;
  border-bottom-width: 0;
  border-top-color: #fff;
}
.popover.right > .arrow {
  top: 50%;
  left: -11px;
  margin-top: -11px;
  border-left-width: 0;
  border-right-color: #999999;
  border-right-color: rgba(0, 0, 0, 0.25);
}
.popover.right > .arrow:after {
  content: " ";
  left: 1px;
  bottom: -10px;
  border-left-width: 0;
  border-right-color: #fff;
}
.popover.bottom > .arrow {
  left: 50%;
  margin-left: -11px;
  border-top-width: 0;
  border-bottom-color: #999999;
  border-bottom-color: rgba(0, 0, 0, 0.25);
  top: -11px;
}
.popover.bottom > .arrow:after {
  content: " ";
  top: 1px;
  margin-left: -10px;
  border-top-width: 0;
  border-bottom-color: #fff;
}
.popover.left > .arrow {
  top: 50%;
  right: -11px;
  margin-top: -11px;
  border-right-width: 0;
  border-left-color: #999999;
  border-left-color: rgba(0, 0, 0, 0.25);
}
.popover.left > .arrow:after {
  content: " ";
  right: 1px;
  border-right-width: 0;
  border-left-color: #fff;
  bottom: -10px;
}
.carousel {
  position: relative;
}
.carousel-inner {
  position: relative;
  overflow: hidden;
  width: 100%;
}
.carousel-inner > .item {
  display: none;
  position: relative;
  -webkit-transition: 0.6s ease-in-out left;
  -o-transition: 0.6s ease-in-out left;
  transition: 0.6s ease-in-out left;
}
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  line-height: 1;
}
@media all and (transform-3d), (-webkit-transform-3d) {
  .carousel-inner > .item {
    -webkit-transition: -webkit-transform 0.6s ease-in-out;
    -moz-transition: -moz-transform 0.6s ease-in-out;
    -o-transition: -o-transform 0.6s ease-in-out;
    transition: transform 0.6s ease-in-out;
    -webkit-backface-visibility: hidden;
    -moz-backface-visibility: hidden;
    backface-visibility: hidden;
    -webkit-perspective: 1000px;
    -moz-perspective: 1000px;
    perspective: 1000px;
  }
  .carousel-inner > .item.next,
  .carousel-inner > .item.active.right {
    -webkit-transform: translate3d(100%, 0, 0);
    transform: translate3d(100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.prev,
  .carousel-inner > .item.active.left {
    -webkit-transform: translate3d(-100%, 0, 0);
    transform: translate3d(-100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.next.left,
  .carousel-inner > .item.prev.right,
  .carousel-inner > .item.active {
    -webkit-transform: translate3d(0, 0, 0);
    transform: translate3d(0, 0, 0);
    left: 0;
  }
}
.carousel-inner > .active,
.carousel-inner > .next,
.carousel-inner > .prev {
  display: block;
}
.carousel-inner > .active {
  left: 0;
}
.carousel-inner > .next,
.carousel-inner > .prev {
  position: absolute;
  top: 0;
  width: 100%;
}
.carousel-inner > .next {
  left: 100%;
}
.carousel-inner > .prev {
  left: -100%;
}
.carousel-inner > .next.left,
.carousel-inner > .prev.right {
  left: 0;
}
.carousel-inner > .active.left {
  left: -100%;
}
.carousel-inner > .active.right {
  left: 100%;
}
.carousel-control {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  width: 15%;
  opacity: 0.5;
  filter: alpha(opacity=50);
  font-size: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
  background-color: rgba(0, 0, 0, 0);
}
.carousel-control.left {
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#80000000', endColorstr='#00000000', GradientType=1);
}
.carousel-control.right {
  left: auto;
  right: 0;
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#00000000', endColorstr='#80000000', GradientType=1);
}
.carousel-control:hover,
.carousel-control:focus {
  outline: 0;
  color: #fff;
  text-decoration: none;
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.carousel-control .icon-prev,
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-left,
.carousel-control .glyphicon-chevron-right {
  position: absolute;
  top: 50%;
  margin-top: -10px;
  z-index: 5;
  display: inline-block;
}
.carousel-control .icon-prev,
.carousel-control .glyphicon-chevron-left {
  left: 50%;
  margin-left: -10px;
}
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-right {
  right: 50%;
  margin-right: -10px;
}
.carousel-control .icon-prev,
.carousel-control .icon-next {
  width: 20px;
  height: 20px;
  line-height: 1;
  font-family: serif;
}
.carousel-control .icon-prev:before {
  content: '\2039';
}
.carousel-control .icon-next:before {
  content: '\203a';
}
.carousel-indicators {
  position: absolute;
  bottom: 10px;
  left: 50%;
  z-index: 15;
  width: 60%;
  margin-left: -30%;
  padding-left: 0;
  list-style: none;
  text-align: center;
}
.carousel-indicators li {
  display: inline-block;
  width: 10px;
  height: 10px;
  margin: 1px;
  text-indent: -999px;
  border: 1px solid #fff;
  border-radius: 10px;
  cursor: pointer;
  background-color: #000 \9;
  background-color: rgba(0, 0, 0, 0);
}
.carousel-indicators .active {
  margin: 0;
  width: 12px;
  height: 12px;
  background-color: #fff;
}
.carousel-caption {
  position: absolute;
  left: 15%;
  right: 15%;
  bottom: 20px;
  z-index: 10;
  padding-top: 20px;
  padding-bottom: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
}
.carousel-caption .btn {
  text-shadow: none;
}
@media screen and (min-width: 768px) {
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-prev,
  .carousel-control .icon-next {
    width: 30px;
    height: 30px;
    margin-top: -10px;
    font-size: 30px;
  }
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .icon-prev {
    margin-left: -10px;
  }
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-next {
    margin-right: -10px;
  }
  .carousel-caption {
    left: 20%;
    right: 20%;
    padding-bottom: 30px;
  }
  .carousel-indicators {
    bottom: 20px;
  }
}
.clearfix:before,
.clearfix:after,
.dl-horizontal dd:before,
.dl-horizontal dd:after,
.container:before,
.container:after,
.container-fluid:before,
.container-fluid:after,
.row:before,
.row:after,
.form-horizontal .form-group:before,
.form-horizontal .form-group:after,
.btn-toolbar:before,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:before,
.btn-group-vertical > .btn-group:after,
.nav:before,
.nav:after,
.navbar:before,
.navbar:after,
.navbar-header:before,
.navbar-header:after,
.navbar-collapse:before,
.navbar-collapse:after,
.pager:before,
.pager:after,
.panel-body:before,
.panel-body:after,
.modal-header:before,
.modal-header:after,
.modal-footer:before,
.modal-footer:after,
.item_buttons:before,
.item_buttons:after {
  content: " ";
  display: table;
}
.clearfix:after,
.dl-horizontal dd:after,
.container:after,
.container-fluid:after,
.row:after,
.form-horizontal .form-group:after,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:after,
.nav:after,
.navbar:after,
.navbar-header:after,
.navbar-collapse:after,
.pager:after,
.panel-body:after,
.modal-header:after,
.modal-footer:after,
.item_buttons:after {
  clear: both;
}
.center-block {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.pull-right {
  float: right !important;
}
.pull-left {
  float: left !important;
}
.hide {
  display: none !important;
}
.show {
  display: block !important;
}
.invisible {
  visibility: hidden;
}
.text-hide {
  font: 0/0 a;
  color: transparent;
  text-shadow: none;
  background-color: transparent;
  border: 0;
}
.hidden {
  display: none !important;
}
.affix {
  position: fixed;
}
@-ms-viewport {
  width: device-width;
}
.visible-xs,
.visible-sm,
.visible-md,
.visible-lg {
  display: none !important;
}
.visible-xs-block,
.visible-xs-inline,
.visible-xs-inline-block,
.visible-sm-block,
.visible-sm-inline,
.visible-sm-inline-block,
.visible-md-block,
.visible-md-inline,
.visible-md-inline-block,
.visible-lg-block,
.visible-lg-inline,
.visible-lg-inline-block {
  display: none !important;
}
@media (max-width: 767px) {
  .visible-xs {
    display: block !important;
  }
  table.visible-xs {
    display: table !important;
  }
  tr.visible-xs {
    display: table-row !important;
  }
  th.visible-xs,
  td.visible-xs {
    display: table-cell !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-block {
    display: block !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline {
    display: inline !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm {
    display: block !important;
  }
  table.visible-sm {
    display: table !important;
  }
  tr.visible-sm {
    display: table-row !important;
  }
  th.visible-sm,
  td.visible-sm {
    display: table-cell !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-block {
    display: block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline {
    display: inline !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md {
    display: block !important;
  }
  table.visible-md {
    display: table !important;
  }
  tr.visible-md {
    display: table-row !important;
  }
  th.visible-md,
  td.visible-md {
    display: table-cell !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-block {
    display: block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline {
    display: inline !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg {
    display: block !important;
  }
  table.visible-lg {
    display: table !important;
  }
  tr.visible-lg {
    display: table-row !important;
  }
  th.visible-lg,
  td.visible-lg {
    display: table-cell !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-block {
    display: block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline {
    display: inline !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline-block {
    display: inline-block !important;
  }
}
@media (max-width: 767px) {
  .hidden-xs {
    display: none !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .hidden-sm {
    display: none !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .hidden-md {
    display: none !important;
  }
}
@media (min-width: 1200px) {
  .hidden-lg {
    display: none !important;
  }
}
.visible-print {
  display: none !important;
}
@media print {
  .visible-print {
    display: block !important;
  }
  table.visible-print {
    display: table !important;
  }
  tr.visible-print {
    display: table-row !important;
  }
  th.visible-print,
  td.visible-print {
    display: table-cell !important;
  }
}
.visible-print-block {
  display: none !important;
}
@media print {
  .visible-print-block {
    display: block !important;
  }
}
.visible-print-inline {
  display: none !important;
}
@media print {
  .visible-print-inline {
    display: inline !important;
  }
}
.visible-print-inline-block {
  display: none !important;
}
@media print {
  .visible-print-inline-block {
    display: inline-block !important;
  }
}
@media print {
  .hidden-print {
    display: none !important;
  }
}
/*!
*
* Font Awesome
*
*/
/*!
 *  Font Awesome 4.7.0 by @davegandy - http://fontawesome.io - @fontawesome
 *  License - http://fontawesome.io/license (Font: SIL OFL 1.1, CSS: MIT License)
 */
/* FONT PATH
 * -------------------------- */
@font-face {
  font-family: 'FontAwesome';
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?v=4.7.0');
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?#iefix&v=4.7.0') format('embedded-opentype'), url('../components/font-awesome/fonts/fontawesome-webfont.woff2?v=4.7.0') format('woff2'), url('../components/font-awesome/fonts/fontawesome-webfont.woff?v=4.7.0') format('woff'), url('../components/font-awesome/fonts/fontawesome-webfont.ttf?v=4.7.0') format('truetype'), url('../components/font-awesome/fonts/fontawesome-webfont.svg?v=4.7.0#fontawesomeregular') format('svg');
  font-weight: normal;
  font-style: normal;
}
.fa {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
/* makes the font 33% larger relative to the icon container */
.fa-lg {
  font-size: 1.33333333em;
  line-height: 0.75em;
  vertical-align: -15%;
}
.fa-2x {
  font-size: 2em;
}
.fa-3x {
  font-size: 3em;
}
.fa-4x {
  font-size: 4em;
}
.fa-5x {
  font-size: 5em;
}
.fa-fw {
  width: 1.28571429em;
  text-align: center;
}
.fa-ul {
  padding-left: 0;
  margin-left: 2.14285714em;
  list-style-type: none;
}
.fa-ul > li {
  position: relative;
}
.fa-li {
  position: absolute;
  left: -2.14285714em;
  width: 2.14285714em;
  top: 0.14285714em;
  text-align: center;
}
.fa-li.fa-lg {
  left: -1.85714286em;
}
.fa-border {
  padding: .2em .25em .15em;
  border: solid 0.08em #eee;
  border-radius: .1em;
}
.fa-pull-left {
  float: left;
}
.fa-pull-right {
  float: right;
}
.fa.fa-pull-left {
  margin-right: .3em;
}
.fa.fa-pull-right {
  margin-left: .3em;
}
/* Deprecated as of 4.4.0 */
.pull-right {
  float: right;
}
.pull-left {
  float: left;
}
.fa.pull-left {
  margin-right: .3em;
}
.fa.pull-right {
  margin-left: .3em;
}
.fa-spin {
  -webkit-animation: fa-spin 2s infinite linear;
  animation: fa-spin 2s infinite linear;
}
.fa-pulse {
  -webkit-animation: fa-spin 1s infinite steps(8);
  animation: fa-spin 1s infinite steps(8);
}
@-webkit-keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
@keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
.fa-rotate-90 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=1)";
  -webkit-transform: rotate(90deg);
  -ms-transform: rotate(90deg);
  transform: rotate(90deg);
}
.fa-rotate-180 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=2)";
  -webkit-transform: rotate(180deg);
  -ms-transform: rotate(180deg);
  transform: rotate(180deg);
}
.fa-rotate-270 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=3)";
  -webkit-transform: rotate(270deg);
  -ms-transform: rotate(270deg);
  transform: rotate(270deg);
}
.fa-flip-horizontal {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=0, mirror=1)";
  -webkit-transform: scale(-1, 1);
  -ms-transform: scale(-1, 1);
  transform: scale(-1, 1);
}
.fa-flip-vertical {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=2, mirror=1)";
  -webkit-transform: scale(1, -1);
  -ms-transform: scale(1, -1);
  transform: scale(1, -1);
}
:root .fa-rotate-90,
:root .fa-rotate-180,
:root .fa-rotate-270,
:root .fa-flip-horizontal,
:root .fa-flip-vertical {
  filter: none;
}
.fa-stack {
  position: relative;
  display: inline-block;
  width: 2em;
  height: 2em;
  line-height: 2em;
  vertical-align: middle;
}
.fa-stack-1x,
.fa-stack-2x {
  position: absolute;
  left: 0;
  width: 100%;
  text-align: center;
}
.fa-stack-1x {
  line-height: inherit;
}
.fa-stack-2x {
  font-size: 2em;
}
.fa-inverse {
  color: #fff;
}
/* Font Awesome uses the Unicode Private Use Area (PUA) to ensure screen
   readers do not read off random characters that represent icons */
.fa-glass:before {
  content: "\f000";
}
.fa-music:before {
  content: "\f001";
}
.fa-search:before {
  content: "\f002";
}
.fa-envelope-o:before {
  content: "\f003";
}
.fa-heart:before {
  content: "\f004";
}
.fa-star:before {
  content: "\f005";
}
.fa-star-o:before {
  content: "\f006";
}
.fa-user:before {
  content: "\f007";
}
.fa-film:before {
  content: "\f008";
}
.fa-th-large:before {
  content: "\f009";
}
.fa-th:before {
  content: "\f00a";
}
.fa-th-list:before {
  content: "\f00b";
}
.fa-check:before {
  content: "\f00c";
}
.fa-remove:before,
.fa-close:before,
.fa-times:before {
  content: "\f00d";
}
.fa-search-plus:before {
  content: "\f00e";
}
.fa-search-minus:before {
  content: "\f010";
}
.fa-power-off:before {
  content: "\f011";
}
.fa-signal:before {
  content: "\f012";
}
.fa-gear:before,
.fa-cog:before {
  content: "\f013";
}
.fa-trash-o:before {
  content: "\f014";
}
.fa-home:before {
  content: "\f015";
}
.fa-file-o:before {
  content: "\f016";
}
.fa-clock-o:before {
  content: "\f017";
}
.fa-road:before {
  content: "\f018";
}
.fa-download:before {
  content: "\f019";
}
.fa-arrow-circle-o-down:before {
  content: "\f01a";
}
.fa-arrow-circle-o-up:before {
  content: "\f01b";
}
.fa-inbox:before {
  content: "\f01c";
}
.fa-play-circle-o:before {
  content: "\f01d";
}
.fa-rotate-right:before,
.fa-repeat:before {
  content: "\f01e";
}
.fa-refresh:before {
  content: "\f021";
}
.fa-list-alt:before {
  content: "\f022";
}
.fa-lock:before {
  content: "\f023";
}
.fa-flag:before {
  content: "\f024";
}
.fa-headphones:before {
  content: "\f025";
}
.fa-volume-off:before {
  content: "\f026";
}
.fa-volume-down:before {
  content: "\f027";
}
.fa-volume-up:before {
  content: "\f028";
}
.fa-qrcode:before {
  content: "\f029";
}
.fa-barcode:before {
  content: "\f02a";
}
.fa-tag:before {
  content: "\f02b";
}
.fa-tags:before {
  content: "\f02c";
}
.fa-book:before {
  content: "\f02d";
}
.fa-bookmark:before {
  content: "\f02e";
}
.fa-print:before {
  content: "\f02f";
}
.fa-camera:before {
  content: "\f030";
}
.fa-font:before {
  content: "\f031";
}
.fa-bold:before {
  content: "\f032";
}
.fa-italic:before {
  content: "\f033";
}
.fa-text-height:before {
  content: "\f034";
}
.fa-text-width:before {
  content: "\f035";
}
.fa-align-left:before {
  content: "\f036";
}
.fa-align-center:before {
  content: "\f037";
}
.fa-align-right:before {
  content: "\f038";
}
.fa-align-justify:before {
  content: "\f039";
}
.fa-list:before {
  content: "\f03a";
}
.fa-dedent:before,
.fa-outdent:before {
  content: "\f03b";
}
.fa-indent:before {
  content: "\f03c";
}
.fa-video-camera:before {
  content: "\f03d";
}
.fa-photo:before,
.fa-image:before,
.fa-picture-o:before {
  content: "\f03e";
}
.fa-pencil:before {
  content: "\f040";
}
.fa-map-marker:before {
  content: "\f041";
}
.fa-adjust:before {
  content: "\f042";
}
.fa-tint:before {
  content: "\f043";
}
.fa-edit:before,
.fa-pencil-square-o:before {
  content: "\f044";
}
.fa-share-square-o:before {
  content: "\f045";
}
.fa-check-square-o:before {
  content: "\f046";
}
.fa-arrows:before {
  content: "\f047";
}
.fa-step-backward:before {
  content: "\f048";
}
.fa-fast-backward:before {
  content: "\f049";
}
.fa-backward:before {
  content: "\f04a";
}
.fa-play:before {
  content: "\f04b";
}
.fa-pause:before {
  content: "\f04c";
}
.fa-stop:before {
  content: "\f04d";
}
.fa-forward:before {
  content: "\f04e";
}
.fa-fast-forward:before {
  content: "\f050";
}
.fa-step-forward:before {
  content: "\f051";
}
.fa-eject:before {
  content: "\f052";
}
.fa-chevron-left:before {
  content: "\f053";
}
.fa-chevron-right:before {
  content: "\f054";
}
.fa-plus-circle:before {
  content: "\f055";
}
.fa-minus-circle:before {
  content: "\f056";
}
.fa-times-circle:before {
  content: "\f057";
}
.fa-check-circle:before {
  content: "\f058";
}
.fa-question-circle:before {
  content: "\f059";
}
.fa-info-circle:before {
  content: "\f05a";
}
.fa-crosshairs:before {
  content: "\f05b";
}
.fa-times-circle-o:before {
  content: "\f05c";
}
.fa-check-circle-o:before {
  content: "\f05d";
}
.fa-ban:before {
  content: "\f05e";
}
.fa-arrow-left:before {
  content: "\f060";
}
.fa-arrow-right:before {
  content: "\f061";
}
.fa-arrow-up:before {
  content: "\f062";
}
.fa-arrow-down:before {
  content: "\f063";
}
.fa-mail-forward:before,
.fa-share:before {
  content: "\f064";
}
.fa-expand:before {
  content: "\f065";
}
.fa-compress:before {
  content: "\f066";
}
.fa-plus:before {
  content: "\f067";
}
.fa-minus:before {
  content: "\f068";
}
.fa-asterisk:before {
  content: "\f069";
}
.fa-exclamation-circle:before {
  content: "\f06a";
}
.fa-gift:before {
  content: "\f06b";
}
.fa-leaf:before {
  content: "\f06c";
}
.fa-fire:before {
  content: "\f06d";
}
.fa-eye:before {
  content: "\f06e";
}
.fa-eye-slash:before {
  content: "\f070";
}
.fa-warning:before,
.fa-exclamation-triangle:before {
  content: "\f071";
}
.fa-plane:before {
  content: "\f072";
}
.fa-calendar:before {
  content: "\f073";
}
.fa-random:before {
  content: "\f074";
}
.fa-comment:before {
  content: "\f075";
}
.fa-magnet:before {
  content: "\f076";
}
.fa-chevron-up:before {
  content: "\f077";
}
.fa-chevron-down:before {
  content: "\f078";
}
.fa-retweet:before {
  content: "\f079";
}
.fa-shopping-cart:before {
  content: "\f07a";
}
.fa-folder:before {
  content: "\f07b";
}
.fa-folder-open:before {
  content: "\f07c";
}
.fa-arrows-v:before {
  content: "\f07d";
}
.fa-arrows-h:before {
  content: "\f07e";
}
.fa-bar-chart-o:before,
.fa-bar-chart:before {
  content: "\f080";
}
.fa-twitter-square:before {
  content: "\f081";
}
.fa-facebook-square:before {
  content: "\f082";
}
.fa-camera-retro:before {
  content: "\f083";
}
.fa-key:before {
  content: "\f084";
}
.fa-gears:before,
.fa-cogs:before {
  content: "\f085";
}
.fa-comments:before {
  content: "\f086";
}
.fa-thumbs-o-up:before {
  content: "\f087";
}
.fa-thumbs-o-down:before {
  content: "\f088";
}
.fa-star-half:before {
  content: "\f089";
}
.fa-heart-o:before {
  content: "\f08a";
}
.fa-sign-out:before {
  content: "\f08b";
}
.fa-linkedin-square:before {
  content: "\f08c";
}
.fa-thumb-tack:before {
  content: "\f08d";
}
.fa-external-link:before {
  content: "\f08e";
}
.fa-sign-in:before {
  content: "\f090";
}
.fa-trophy:before {
  content: "\f091";
}
.fa-github-square:before {
  content: "\f092";
}
.fa-upload:before {
  content: "\f093";
}
.fa-lemon-o:before {
  content: "\f094";
}
.fa-phone:before {
  content: "\f095";
}
.fa-square-o:before {
  content: "\f096";
}
.fa-bookmark-o:before {
  content: "\f097";
}
.fa-phone-square:before {
  content: "\f098";
}
.fa-twitter:before {
  content: "\f099";
}
.fa-facebook-f:before,
.fa-facebook:before {
  content: "\f09a";
}
.fa-github:before {
  content: "\f09b";
}
.fa-unlock:before {
  content: "\f09c";
}
.fa-credit-card:before {
  content: "\f09d";
}
.fa-feed:before,
.fa-rss:before {
  content: "\f09e";
}
.fa-hdd-o:before {
  content: "\f0a0";
}
.fa-bullhorn:before {
  content: "\f0a1";
}
.fa-bell:before {
  content: "\f0f3";
}
.fa-certificate:before {
  content: "\f0a3";
}
.fa-hand-o-right:before {
  content: "\f0a4";
}
.fa-hand-o-left:before {
  content: "\f0a5";
}
.fa-hand-o-up:before {
  content: "\f0a6";
}
.fa-hand-o-down:before {
  content: "\f0a7";
}
.fa-arrow-circle-left:before {
  content: "\f0a8";
}
.fa-arrow-circle-right:before {
  content: "\f0a9";
}
.fa-arrow-circle-up:before {
  content: "\f0aa";
}
.fa-arrow-circle-down:before {
  content: "\f0ab";
}
.fa-globe:before {
  content: "\f0ac";
}
.fa-wrench:before {
  content: "\f0ad";
}
.fa-tasks:before {
  content: "\f0ae";
}
.fa-filter:before {
  content: "\f0b0";
}
.fa-briefcase:before {
  content: "\f0b1";
}
.fa-arrows-alt:before {
  content: "\f0b2";
}
.fa-group:before,
.fa-users:before {
  content: "\f0c0";
}
.fa-chain:before,
.fa-link:before {
  content: "\f0c1";
}
.fa-cloud:before {
  content: "\f0c2";
}
.fa-flask:before {
  content: "\f0c3";
}
.fa-cut:before,
.fa-scissors:before {
  content: "\f0c4";
}
.fa-copy:before,
.fa-files-o:before {
  content: "\f0c5";
}
.fa-paperclip:before {
  content: "\f0c6";
}
.fa-save:before,
.fa-floppy-o:before {
  content: "\f0c7";
}
.fa-square:before {
  content: "\f0c8";
}
.fa-navicon:before,
.fa-reorder:before,
.fa-bars:before {
  content: "\f0c9";
}
.fa-list-ul:before {
  content: "\f0ca";
}
.fa-list-ol:before {
  content: "\f0cb";
}
.fa-strikethrough:before {
  content: "\f0cc";
}
.fa-underline:before {
  content: "\f0cd";
}
.fa-table:before {
  content: "\f0ce";
}
.fa-magic:before {
  content: "\f0d0";
}
.fa-truck:before {
  content: "\f0d1";
}
.fa-pinterest:before {
  content: "\f0d2";
}
.fa-pinterest-square:before {
  content: "\f0d3";
}
.fa-google-plus-square:before {
  content: "\f0d4";
}
.fa-google-plus:before {
  content: "\f0d5";
}
.fa-money:before {
  content: "\f0d6";
}
.fa-caret-down:before {
  content: "\f0d7";
}
.fa-caret-up:before {
  content: "\f0d8";
}
.fa-caret-left:before {
  content: "\f0d9";
}
.fa-caret-right:before {
  content: "\f0da";
}
.fa-columns:before {
  content: "\f0db";
}
.fa-unsorted:before,
.fa-sort:before {
  content: "\f0dc";
}
.fa-sort-down:before,
.fa-sort-desc:before {
  content: "\f0dd";
}
.fa-sort-up:before,
.fa-sort-asc:before {
  content: "\f0de";
}
.fa-envelope:before {
  content: "\f0e0";
}
.fa-linkedin:before {
  content: "\f0e1";
}
.fa-rotate-left:before,
.fa-undo:before {
  content: "\f0e2";
}
.fa-legal:before,
.fa-gavel:before {
  content: "\f0e3";
}
.fa-dashboard:before,
.fa-tachometer:before {
  content: "\f0e4";
}
.fa-comment-o:before {
  content: "\f0e5";
}
.fa-comments-o:before {
  content: "\f0e6";
}
.fa-flash:before,
.fa-bolt:before {
  content: "\f0e7";
}
.fa-sitemap:before {
  content: "\f0e8";
}
.fa-umbrella:before {
  content: "\f0e9";
}
.fa-paste:before,
.fa-clipboard:before {
  content: "\f0ea";
}
.fa-lightbulb-o:before {
  content: "\f0eb";
}
.fa-exchange:before {
  content: "\f0ec";
}
.fa-cloud-download:before {
  content: "\f0ed";
}
.fa-cloud-upload:before {
  content: "\f0ee";
}
.fa-user-md:before {
  content: "\f0f0";
}
.fa-stethoscope:before {
  content: "\f0f1";
}
.fa-suitcase:before {
  content: "\f0f2";
}
.fa-bell-o:before {
  content: "\f0a2";
}
.fa-coffee:before {
  content: "\f0f4";
}
.fa-cutlery:before {
  content: "\f0f5";
}
.fa-file-text-o:before {
  content: "\f0f6";
}
.fa-building-o:before {
  content: "\f0f7";
}
.fa-hospital-o:before {
  content: "\f0f8";
}
.fa-ambulance:before {
  content: "\f0f9";
}
.fa-medkit:before {
  content: "\f0fa";
}
.fa-fighter-jet:before {
  content: "\f0fb";
}
.fa-beer:before {
  content: "\f0fc";
}
.fa-h-square:before {
  content: "\f0fd";
}
.fa-plus-square:before {
  content: "\f0fe";
}
.fa-angle-double-left:before {
  content: "\f100";
}
.fa-angle-double-right:before {
  content: "\f101";
}
.fa-angle-double-up:before {
  content: "\f102";
}
.fa-angle-double-down:before {
  content: "\f103";
}
.fa-angle-left:before {
  content: "\f104";
}
.fa-angle-right:before {
  content: "\f105";
}
.fa-angle-up:before {
  content: "\f106";
}
.fa-angle-down:before {
  content: "\f107";
}
.fa-desktop:before {
  content: "\f108";
}
.fa-laptop:before {
  content: "\f109";
}
.fa-tablet:before {
  content: "\f10a";
}
.fa-mobile-phone:before,
.fa-mobile:before {
  content: "\f10b";
}
.fa-circle-o:before {
  content: "\f10c";
}
.fa-quote-left:before {
  content: "\f10d";
}
.fa-quote-right:before {
  content: "\f10e";
}
.fa-spinner:before {
  content: "\f110";
}
.fa-circle:before {
  content: "\f111";
}
.fa-mail-reply:before,
.fa-reply:before {
  content: "\f112";
}
.fa-github-alt:before {
  content: "\f113";
}
.fa-folder-o:before {
  content: "\f114";
}
.fa-folder-open-o:before {
  content: "\f115";
}
.fa-smile-o:before {
  content: "\f118";
}
.fa-frown-o:before {
  content: "\f119";
}
.fa-meh-o:before {
  content: "\f11a";
}
.fa-gamepad:before {
  content: "\f11b";
}
.fa-keyboard-o:before {
  content: "\f11c";
}
.fa-flag-o:before {
  content: "\f11d";
}
.fa-flag-checkered:before {
  content: "\f11e";
}
.fa-terminal:before {
  content: "\f120";
}
.fa-code:before {
  content: "\f121";
}
.fa-mail-reply-all:before,
.fa-reply-all:before {
  content: "\f122";
}
.fa-star-half-empty:before,
.fa-star-half-full:before,
.fa-star-half-o:before {
  content: "\f123";
}
.fa-location-arrow:before {
  content: "\f124";
}
.fa-crop:before {
  content: "\f125";
}
.fa-code-fork:before {
  content: "\f126";
}
.fa-unlink:before,
.fa-chain-broken:before {
  content: "\f127";
}
.fa-question:before {
  content: "\f128";
}
.fa-info:before {
  content: "\f129";
}
.fa-exclamation:before {
  content: "\f12a";
}
.fa-superscript:before {
  content: "\f12b";
}
.fa-subscript:before {
  content: "\f12c";
}
.fa-eraser:before {
  content: "\f12d";
}
.fa-puzzle-piece:before {
  content: "\f12e";
}
.fa-microphone:before {
  content: "\f130";
}
.fa-microphone-slash:before {
  content: "\f131";
}
.fa-shield:before {
  content: "\f132";
}
.fa-calendar-o:before {
  content: "\f133";
}
.fa-fire-extinguisher:before {
  content: "\f134";
}
.fa-rocket:before {
  content: "\f135";
}
.fa-maxcdn:before {
  content: "\f136";
}
.fa-chevron-circle-left:before {
  content: "\f137";
}
.fa-chevron-circle-right:before {
  content: "\f138";
}
.fa-chevron-circle-up:before {
  content: "\f139";
}
.fa-chevron-circle-down:before {
  content: "\f13a";
}
.fa-html5:before {
  content: "\f13b";
}
.fa-css3:before {
  content: "\f13c";
}
.fa-anchor:before {
  content: "\f13d";
}
.fa-unlock-alt:before {
  content: "\f13e";
}
.fa-bullseye:before {
  content: "\f140";
}
.fa-ellipsis-h:before {
  content: "\f141";
}
.fa-ellipsis-v:before {
  content: "\f142";
}
.fa-rss-square:before {
  content: "\f143";
}
.fa-play-circle:before {
  content: "\f144";
}
.fa-ticket:before {
  content: "\f145";
}
.fa-minus-square:before {
  content: "\f146";
}
.fa-minus-square-o:before {
  content: "\f147";
}
.fa-level-up:before {
  content: "\f148";
}
.fa-level-down:before {
  content: "\f149";
}
.fa-check-square:before {
  content: "\f14a";
}
.fa-pencil-square:before {
  content: "\f14b";
}
.fa-external-link-square:before {
  content: "\f14c";
}
.fa-share-square:before {
  content: "\f14d";
}
.fa-compass:before {
  content: "\f14e";
}
.fa-toggle-down:before,
.fa-caret-square-o-down:before {
  content: "\f150";
}
.fa-toggle-up:before,
.fa-caret-square-o-up:before {
  content: "\f151";
}
.fa-toggle-right:before,
.fa-caret-square-o-right:before {
  content: "\f152";
}
.fa-euro:before,
.fa-eur:before {
  content: "\f153";
}
.fa-gbp:before {
  content: "\f154";
}
.fa-dollar:before,
.fa-usd:before {
  content: "\f155";
}
.fa-rupee:before,
.fa-inr:before {
  content: "\f156";
}
.fa-cny:before,
.fa-rmb:before,
.fa-yen:before,
.fa-jpy:before {
  content: "\f157";
}
.fa-ruble:before,
.fa-rouble:before,
.fa-rub:before {
  content: "\f158";
}
.fa-won:before,
.fa-krw:before {
  content: "\f159";
}
.fa-bitcoin:before,
.fa-btc:before {
  content: "\f15a";
}
.fa-file:before {
  content: "\f15b";
}
.fa-file-text:before {
  content: "\f15c";
}
.fa-sort-alpha-asc:before {
  content: "\f15d";
}
.fa-sort-alpha-desc:before {
  content: "\f15e";
}
.fa-sort-amount-asc:before {
  content: "\f160";
}
.fa-sort-amount-desc:before {
  content: "\f161";
}
.fa-sort-numeric-asc:before {
  content: "\f162";
}
.fa-sort-numeric-desc:before {
  content: "\f163";
}
.fa-thumbs-up:before {
  content: "\f164";
}
.fa-thumbs-down:before {
  content: "\f165";
}
.fa-youtube-square:before {
  content: "\f166";
}
.fa-youtube:before {
  content: "\f167";
}
.fa-xing:before {
  content: "\f168";
}
.fa-xing-square:before {
  content: "\f169";
}
.fa-youtube-play:before {
  content: "\f16a";
}
.fa-dropbox:before {
  content: "\f16b";
}
.fa-stack-overflow:before {
  content: "\f16c";
}
.fa-instagram:before {
  content: "\f16d";
}
.fa-flickr:before {
  content: "\f16e";
}
.fa-adn:before {
  content: "\f170";
}
.fa-bitbucket:before {
  content: "\f171";
}
.fa-bitbucket-square:before {
  content: "\f172";
}
.fa-tumblr:before {
  content: "\f173";
}
.fa-tumblr-square:before {
  content: "\f174";
}
.fa-long-arrow-down:before {
  content: "\f175";
}
.fa-long-arrow-up:before {
  content: "\f176";
}
.fa-long-arrow-left:before {
  content: "\f177";
}
.fa-long-arrow-right:before {
  content: "\f178";
}
.fa-apple:before {
  content: "\f179";
}
.fa-windows:before {
  content: "\f17a";
}
.fa-android:before {
  content: "\f17b";
}
.fa-linux:before {
  content: "\f17c";
}
.fa-dribbble:before {
  content: "\f17d";
}
.fa-skype:before {
  content: "\f17e";
}
.fa-foursquare:before {
  content: "\f180";
}
.fa-trello:before {
  content: "\f181";
}
.fa-female:before {
  content: "\f182";
}
.fa-male:before {
  content: "\f183";
}
.fa-gittip:before,
.fa-gratipay:before {
  content: "\f184";
}
.fa-sun-o:before {
  content: "\f185";
}
.fa-moon-o:before {
  content: "\f186";
}
.fa-archive:before {
  content: "\f187";
}
.fa-bug:before {
  content: "\f188";
}
.fa-vk:before {
  content: "\f189";
}
.fa-weibo:before {
  content: "\f18a";
}
.fa-renren:before {
  content: "\f18b";
}
.fa-pagelines:before {
  content: "\f18c";
}
.fa-stack-exchange:before {
  content: "\f18d";
}
.fa-arrow-circle-o-right:before {
  content: "\f18e";
}
.fa-arrow-circle-o-left:before {
  content: "\f190";
}
.fa-toggle-left:before,
.fa-caret-square-o-left:before {
  content: "\f191";
}
.fa-dot-circle-o:before {
  content: "\f192";
}
.fa-wheelchair:before {
  content: "\f193";
}
.fa-vimeo-square:before {
  content: "\f194";
}
.fa-turkish-lira:before,
.fa-try:before {
  content: "\f195";
}
.fa-plus-square-o:before {
  content: "\f196";
}
.fa-space-shuttle:before {
  content: "\f197";
}
.fa-slack:before {
  content: "\f198";
}
.fa-envelope-square:before {
  content: "\f199";
}
.fa-wordpress:before {
  content: "\f19a";
}
.fa-openid:before {
  content: "\f19b";
}
.fa-institution:before,
.fa-bank:before,
.fa-university:before {
  content: "\f19c";
}
.fa-mortar-board:before,
.fa-graduation-cap:before {
  content: "\f19d";
}
.fa-yahoo:before {
  content: "\f19e";
}
.fa-google:before {
  content: "\f1a0";
}
.fa-reddit:before {
  content: "\f1a1";
}
.fa-reddit-square:before {
  content: "\f1a2";
}
.fa-stumbleupon-circle:before {
  content: "\f1a3";
}
.fa-stumbleupon:before {
  content: "\f1a4";
}
.fa-delicious:before {
  content: "\f1a5";
}
.fa-digg:before {
  content: "\f1a6";
}
.fa-pied-piper-pp:before {
  content: "\f1a7";
}
.fa-pied-piper-alt:before {
  content: "\f1a8";
}
.fa-drupal:before {
  content: "\f1a9";
}
.fa-joomla:before {
  content: "\f1aa";
}
.fa-language:before {
  content: "\f1ab";
}
.fa-fax:before {
  content: "\f1ac";
}
.fa-building:before {
  content: "\f1ad";
}
.fa-child:before {
  content: "\f1ae";
}
.fa-paw:before {
  content: "\f1b0";
}
.fa-spoon:before {
  content: "\f1b1";
}
.fa-cube:before {
  content: "\f1b2";
}
.fa-cubes:before {
  content: "\f1b3";
}
.fa-behance:before {
  content: "\f1b4";
}
.fa-behance-square:before {
  content: "\f1b5";
}
.fa-steam:before {
  content: "\f1b6";
}
.fa-steam-square:before {
  content: "\f1b7";
}
.fa-recycle:before {
  content: "\f1b8";
}
.fa-automobile:before,
.fa-car:before {
  content: "\f1b9";
}
.fa-cab:before,
.fa-taxi:before {
  content: "\f1ba";
}
.fa-tree:before {
  content: "\f1bb";
}
.fa-spotify:before {
  content: "\f1bc";
}
.fa-deviantart:before {
  content: "\f1bd";
}
.fa-soundcloud:before {
  content: "\f1be";
}
.fa-database:before {
  content: "\f1c0";
}
.fa-file-pdf-o:before {
  content: "\f1c1";
}
.fa-file-word-o:before {
  content: "\f1c2";
}
.fa-file-excel-o:before {
  content: "\f1c3";
}
.fa-file-powerpoint-o:before {
  content: "\f1c4";
}
.fa-file-photo-o:before,
.fa-file-picture-o:before,
.fa-file-image-o:before {
  content: "\f1c5";
}
.fa-file-zip-o:before,
.fa-file-archive-o:before {
  content: "\f1c6";
}
.fa-file-sound-o:before,
.fa-file-audio-o:before {
  content: "\f1c7";
}
.fa-file-movie-o:before,
.fa-file-video-o:before {
  content: "\f1c8";
}
.fa-file-code-o:before {
  content: "\f1c9";
}
.fa-vine:before {
  content: "\f1ca";
}
.fa-codepen:before {
  content: "\f1cb";
}
.fa-jsfiddle:before {
  content: "\f1cc";
}
.fa-life-bouy:before,
.fa-life-buoy:before,
.fa-life-saver:before,
.fa-support:before,
.fa-life-ring:before {
  content: "\f1cd";
}
.fa-circle-o-notch:before {
  content: "\f1ce";
}
.fa-ra:before,
.fa-resistance:before,
.fa-rebel:before {
  content: "\f1d0";
}
.fa-ge:before,
.fa-empire:before {
  content: "\f1d1";
}
.fa-git-square:before {
  content: "\f1d2";
}
.fa-git:before {
  content: "\f1d3";
}
.fa-y-combinator-square:before,
.fa-yc-square:before,
.fa-hacker-news:before {
  content: "\f1d4";
}
.fa-tencent-weibo:before {
  content: "\f1d5";
}
.fa-qq:before {
  content: "\f1d6";
}
.fa-wechat:before,
.fa-weixin:before {
  content: "\f1d7";
}
.fa-send:before,
.fa-paper-plane:before {
  content: "\f1d8";
}
.fa-send-o:before,
.fa-paper-plane-o:before {
  content: "\f1d9";
}
.fa-history:before {
  content: "\f1da";
}
.fa-circle-thin:before {
  content: "\f1db";
}
.fa-header:before {
  content: "\f1dc";
}
.fa-paragraph:before {
  content: "\f1dd";
}
.fa-sliders:before {
  content: "\f1de";
}
.fa-share-alt:before {
  content: "\f1e0";
}
.fa-share-alt-square:before {
  content: "\f1e1";
}
.fa-bomb:before {
  content: "\f1e2";
}
.fa-soccer-ball-o:before,
.fa-futbol-o:before {
  content: "\f1e3";
}
.fa-tty:before {
  content: "\f1e4";
}
.fa-binoculars:before {
  content: "\f1e5";
}
.fa-plug:before {
  content: "\f1e6";
}
.fa-slideshare:before {
  content: "\f1e7";
}
.fa-twitch:before {
  content: "\f1e8";
}
.fa-yelp:before {
  content: "\f1e9";
}
.fa-newspaper-o:before {
  content: "\f1ea";
}
.fa-wifi:before {
  content: "\f1eb";
}
.fa-calculator:before {
  content: "\f1ec";
}
.fa-paypal:before {
  content: "\f1ed";
}
.fa-google-wallet:before {
  content: "\f1ee";
}
.fa-cc-visa:before {
  content: "\f1f0";
}
.fa-cc-mastercard:before {
  content: "\f1f1";
}
.fa-cc-discover:before {
  content: "\f1f2";
}
.fa-cc-amex:before {
  content: "\f1f3";
}
.fa-cc-paypal:before {
  content: "\f1f4";
}
.fa-cc-stripe:before {
  content: "\f1f5";
}
.fa-bell-slash:before {
  content: "\f1f6";
}
.fa-bell-slash-o:before {
  content: "\f1f7";
}
.fa-trash:before {
  content: "\f1f8";
}
.fa-copyright:before {
  content: "\f1f9";
}
.fa-at:before {
  content: "\f1fa";
}
.fa-eyedropper:before {
  content: "\f1fb";
}
.fa-paint-brush:before {
  content: "\f1fc";
}
.fa-birthday-cake:before {
  content: "\f1fd";
}
.fa-area-chart:before {
  content: "\f1fe";
}
.fa-pie-chart:before {
  content: "\f200";
}
.fa-line-chart:before {
  content: "\f201";
}
.fa-lastfm:before {
  content: "\f202";
}
.fa-lastfm-square:before {
  content: "\f203";
}
.fa-toggle-off:before {
  content: "\f204";
}
.fa-toggle-on:before {
  content: "\f205";
}
.fa-bicycle:before {
  content: "\f206";
}
.fa-bus:before {
  content: "\f207";
}
.fa-ioxhost:before {
  content: "\f208";
}
.fa-angellist:before {
  content: "\f209";
}
.fa-cc:before {
  content: "\f20a";
}
.fa-shekel:before,
.fa-sheqel:before,
.fa-ils:before {
  content: "\f20b";
}
.fa-meanpath:before {
  content: "\f20c";
}
.fa-buysellads:before {
  content: "\f20d";
}
.fa-connectdevelop:before {
  content: "\f20e";
}
.fa-dashcube:before {
  content: "\f210";
}
.fa-forumbee:before {
  content: "\f211";
}
.fa-leanpub:before {
  content: "\f212";
}
.fa-sellsy:before {
  content: "\f213";
}
.fa-shirtsinbulk:before {
  content: "\f214";
}
.fa-simplybuilt:before {
  content: "\f215";
}
.fa-skyatlas:before {
  content: "\f216";
}
.fa-cart-plus:before {
  content: "\f217";
}
.fa-cart-arrow-down:before {
  content: "\f218";
}
.fa-diamond:before {
  content: "\f219";
}
.fa-ship:before {
  content: "\f21a";
}
.fa-user-secret:before {
  content: "\f21b";
}
.fa-motorcycle:before {
  content: "\f21c";
}
.fa-street-view:before {
  content: "\f21d";
}
.fa-heartbeat:before {
  content: "\f21e";
}
.fa-venus:before {
  content: "\f221";
}
.fa-mars:before {
  content: "\f222";
}
.fa-mercury:before {
  content: "\f223";
}
.fa-intersex:before,
.fa-transgender:before {
  content: "\f224";
}
.fa-transgender-alt:before {
  content: "\f225";
}
.fa-venus-double:before {
  content: "\f226";
}
.fa-mars-double:before {
  content: "\f227";
}
.fa-venus-mars:before {
  content: "\f228";
}
.fa-mars-stroke:before {
  content: "\f229";
}
.fa-mars-stroke-v:before {
  content: "\f22a";
}
.fa-mars-stroke-h:before {
  content: "\f22b";
}
.fa-neuter:before {
  content: "\f22c";
}
.fa-genderless:before {
  content: "\f22d";
}
.fa-facebook-official:before {
  content: "\f230";
}
.fa-pinterest-p:before {
  content: "\f231";
}
.fa-whatsapp:before {
  content: "\f232";
}
.fa-server:before {
  content: "\f233";
}
.fa-user-plus:before {
  content: "\f234";
}
.fa-user-times:before {
  content: "\f235";
}
.fa-hotel:before,
.fa-bed:before {
  content: "\f236";
}
.fa-viacoin:before {
  content: "\f237";
}
.fa-train:before {
  content: "\f238";
}
.fa-subway:before {
  content: "\f239";
}
.fa-medium:before {
  content: "\f23a";
}
.fa-yc:before,
.fa-y-combinator:before {
  content: "\f23b";
}
.fa-optin-monster:before {
  content: "\f23c";
}
.fa-opencart:before {
  content: "\f23d";
}
.fa-expeditedssl:before {
  content: "\f23e";
}
.fa-battery-4:before,
.fa-battery:before,
.fa-battery-full:before {
  content: "\f240";
}
.fa-battery-3:before,
.fa-battery-three-quarters:before {
  content: "\f241";
}
.fa-battery-2:before,
.fa-battery-half:before {
  content: "\f242";
}
.fa-battery-1:before,
.fa-battery-quarter:before {
  content: "\f243";
}
.fa-battery-0:before,
.fa-battery-empty:before {
  content: "\f244";
}
.fa-mouse-pointer:before {
  content: "\f245";
}
.fa-i-cursor:before {
  content: "\f246";
}
.fa-object-group:before {
  content: "\f247";
}
.fa-object-ungroup:before {
  content: "\f248";
}
.fa-sticky-note:before {
  content: "\f249";
}
.fa-sticky-note-o:before {
  content: "\f24a";
}
.fa-cc-jcb:before {
  content: "\f24b";
}
.fa-cc-diners-club:before {
  content: "\f24c";
}
.fa-clone:before {
  content: "\f24d";
}
.fa-balance-scale:before {
  content: "\f24e";
}
.fa-hourglass-o:before {
  content: "\f250";
}
.fa-hourglass-1:before,
.fa-hourglass-start:before {
  content: "\f251";
}
.fa-hourglass-2:before,
.fa-hourglass-half:before {
  content: "\f252";
}
.fa-hourglass-3:before,
.fa-hourglass-end:before {
  content: "\f253";
}
.fa-hourglass:before {
  content: "\f254";
}
.fa-hand-grab-o:before,
.fa-hand-rock-o:before {
  content: "\f255";
}
.fa-hand-stop-o:before,
.fa-hand-paper-o:before {
  content: "\f256";
}
.fa-hand-scissors-o:before {
  content: "\f257";
}
.fa-hand-lizard-o:before {
  content: "\f258";
}
.fa-hand-spock-o:before {
  content: "\f259";
}
.fa-hand-pointer-o:before {
  content: "\f25a";
}
.fa-hand-peace-o:before {
  content: "\f25b";
}
.fa-trademark:before {
  content: "\f25c";
}
.fa-registered:before {
  content: "\f25d";
}
.fa-creative-commons:before {
  content: "\f25e";
}
.fa-gg:before {
  content: "\f260";
}
.fa-gg-circle:before {
  content: "\f261";
}
.fa-tripadvisor:before {
  content: "\f262";
}
.fa-odnoklassniki:before {
  content: "\f263";
}
.fa-odnoklassniki-square:before {
  content: "\f264";
}
.fa-get-pocket:before {
  content: "\f265";
}
.fa-wikipedia-w:before {
  content: "\f266";
}
.fa-safari:before {
  content: "\f267";
}
.fa-chrome:before {
  content: "\f268";
}
.fa-firefox:before {
  content: "\f269";
}
.fa-opera:before {
  content: "\f26a";
}
.fa-internet-explorer:before {
  content: "\f26b";
}
.fa-tv:before,
.fa-television:before {
  content: "\f26c";
}
.fa-contao:before {
  content: "\f26d";
}
.fa-500px:before {
  content: "\f26e";
}
.fa-amazon:before {
  content: "\f270";
}
.fa-calendar-plus-o:before {
  content: "\f271";
}
.fa-calendar-minus-o:before {
  content: "\f272";
}
.fa-calendar-times-o:before {
  content: "\f273";
}
.fa-calendar-check-o:before {
  content: "\f274";
}
.fa-industry:before {
  content: "\f275";
}
.fa-map-pin:before {
  content: "\f276";
}
.fa-map-signs:before {
  content: "\f277";
}
.fa-map-o:before {
  content: "\f278";
}
.fa-map:before {
  content: "\f279";
}
.fa-commenting:before {
  content: "\f27a";
}
.fa-commenting-o:before {
  content: "\f27b";
}
.fa-houzz:before {
  content: "\f27c";
}
.fa-vimeo:before {
  content: "\f27d";
}
.fa-black-tie:before {
  content: "\f27e";
}
.fa-fonticons:before {
  content: "\f280";
}
.fa-reddit-alien:before {
  content: "\f281";
}
.fa-edge:before {
  content: "\f282";
}
.fa-credit-card-alt:before {
  content: "\f283";
}
.fa-codiepie:before {
  content: "\f284";
}
.fa-modx:before {
  content: "\f285";
}
.fa-fort-awesome:before {
  content: "\f286";
}
.fa-usb:before {
  content: "\f287";
}
.fa-product-hunt:before {
  content: "\f288";
}
.fa-mixcloud:before {
  content: "\f289";
}
.fa-scribd:before {
  content: "\f28a";
}
.fa-pause-circle:before {
  content: "\f28b";
}
.fa-pause-circle-o:before {
  content: "\f28c";
}
.fa-stop-circle:before {
  content: "\f28d";
}
.fa-stop-circle-o:before {
  content: "\f28e";
}
.fa-shopping-bag:before {
  content: "\f290";
}
.fa-shopping-basket:before {
  content: "\f291";
}
.fa-hashtag:before {
  content: "\f292";
}
.fa-bluetooth:before {
  content: "\f293";
}
.fa-bluetooth-b:before {
  content: "\f294";
}
.fa-percent:before {
  content: "\f295";
}
.fa-gitlab:before {
  content: "\f296";
}
.fa-wpbeginner:before {
  content: "\f297";
}
.fa-wpforms:before {
  content: "\f298";
}
.fa-envira:before {
  content: "\f299";
}
.fa-universal-access:before {
  content: "\f29a";
}
.fa-wheelchair-alt:before {
  content: "\f29b";
}
.fa-question-circle-o:before {
  content: "\f29c";
}
.fa-blind:before {
  content: "\f29d";
}
.fa-audio-description:before {
  content: "\f29e";
}
.fa-volume-control-phone:before {
  content: "\f2a0";
}
.fa-braille:before {
  content: "\f2a1";
}
.fa-assistive-listening-systems:before {
  content: "\f2a2";
}
.fa-asl-interpreting:before,
.fa-american-sign-language-interpreting:before {
  content: "\f2a3";
}
.fa-deafness:before,
.fa-hard-of-hearing:before,
.fa-deaf:before {
  content: "\f2a4";
}
.fa-glide:before {
  content: "\f2a5";
}
.fa-glide-g:before {
  content: "\f2a6";
}
.fa-signing:before,
.fa-sign-language:before {
  content: "\f2a7";
}
.fa-low-vision:before {
  content: "\f2a8";
}
.fa-viadeo:before {
  content: "\f2a9";
}
.fa-viadeo-square:before {
  content: "\f2aa";
}
.fa-snapchat:before {
  content: "\f2ab";
}
.fa-snapchat-ghost:before {
  content: "\f2ac";
}
.fa-snapchat-square:before {
  content: "\f2ad";
}
.fa-pied-piper:before {
  content: "\f2ae";
}
.fa-first-order:before {
  content: "\f2b0";
}
.fa-yoast:before {
  content: "\f2b1";
}
.fa-themeisle:before {
  content: "\f2b2";
}
.fa-google-plus-circle:before,
.fa-google-plus-official:before {
  content: "\f2b3";
}
.fa-fa:before,
.fa-font-awesome:before {
  content: "\f2b4";
}
.fa-handshake-o:before {
  content: "\f2b5";
}
.fa-envelope-open:before {
  content: "\f2b6";
}
.fa-envelope-open-o:before {
  content: "\f2b7";
}
.fa-linode:before {
  content: "\f2b8";
}
.fa-address-book:before {
  content: "\f2b9";
}
.fa-address-book-o:before {
  content: "\f2ba";
}
.fa-vcard:before,
.fa-address-card:before {
  content: "\f2bb";
}
.fa-vcard-o:before,
.fa-address-card-o:before {
  content: "\f2bc";
}
.fa-user-circle:before {
  content: "\f2bd";
}
.fa-user-circle-o:before {
  content: "\f2be";
}
.fa-user-o:before {
  content: "\f2c0";
}
.fa-id-badge:before {
  content: "\f2c1";
}
.fa-drivers-license:before,
.fa-id-card:before {
  content: "\f2c2";
}
.fa-drivers-license-o:before,
.fa-id-card-o:before {
  content: "\f2c3";
}
.fa-quora:before {
  content: "\f2c4";
}
.fa-free-code-camp:before {
  content: "\f2c5";
}
.fa-telegram:before {
  content: "\f2c6";
}
.fa-thermometer-4:before,
.fa-thermometer:before,
.fa-thermometer-full:before {
  content: "\f2c7";
}
.fa-thermometer-3:before,
.fa-thermometer-three-quarters:before {
  content: "\f2c8";
}
.fa-thermometer-2:before,
.fa-thermometer-half:before {
  content: "\f2c9";
}
.fa-thermometer-1:before,
.fa-thermometer-quarter:before {
  content: "\f2ca";
}
.fa-thermometer-0:before,
.fa-thermometer-empty:before {
  content: "\f2cb";
}
.fa-shower:before {
  content: "\f2cc";
}
.fa-bathtub:before,
.fa-s15:before,
.fa-bath:before {
  content: "\f2cd";
}
.fa-podcast:before {
  content: "\f2ce";
}
.fa-window-maximize:before {
  content: "\f2d0";
}
.fa-window-minimize:before {
  content: "\f2d1";
}
.fa-window-restore:before {
  content: "\f2d2";
}
.fa-times-rectangle:before,
.fa-window-close:before {
  content: "\f2d3";
}
.fa-times-rectangle-o:before,
.fa-window-close-o:before {
  content: "\f2d4";
}
.fa-bandcamp:before {
  content: "\f2d5";
}
.fa-grav:before {
  content: "\f2d6";
}
.fa-etsy:before {
  content: "\f2d7";
}
.fa-imdb:before {
  content: "\f2d8";
}
.fa-ravelry:before {
  content: "\f2d9";
}
.fa-eercast:before {
  content: "\f2da";
}
.fa-microchip:before {
  content: "\f2db";
}
.fa-snowflake-o:before {
  content: "\f2dc";
}
.fa-superpowers:before {
  content: "\f2dd";
}
.fa-wpexplorer:before {
  content: "\f2de";
}
.fa-meetup:before {
  content: "\f2e0";
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
/*!
*
* IPython base
*
*/
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
code {
  color: #000;
}
pre {
  font-size: inherit;
  line-height: inherit;
}
label {
  font-weight: normal;
}
/* Make the page background atleast 100% the height of the view port */
/* Make the page itself atleast 70% the height of the view port */
.border-box-sizing {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.corner-all {
  border-radius: 2px;
}
.no-padding {
  padding: 0px;
}
/* Flexible box model classes */
/* Taken from Alex Russell http://infrequently.org/2009/08/css-3-progress/ */
/* This file is a compatability layer.  It allows the usage of flexible box 
model layouts accross multiple browsers, including older browsers.  The newest,
universal implementation of the flexible box model is used when available (see
`Modern browsers` comments below).  Browsers that are known to implement this 
new spec completely include:

    Firefox 28.0+
    Chrome 29.0+
    Internet Explorer 11+ 
    Opera 17.0+

Browsers not listed, including Safari, are supported via the styling under the
`Old browsers` comments below.
*/
.hbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
.hbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.vbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
.vbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.hbox.reverse,
.vbox.reverse,
.reverse {
  /* Old browsers */
  -webkit-box-direction: reverse;
  -moz-box-direction: reverse;
  box-direction: reverse;
  /* Modern browsers */
  flex-direction: row-reverse;
}
.hbox.box-flex0,
.vbox.box-flex0,
.box-flex0 {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
  width: auto;
}
.hbox.box-flex1,
.vbox.box-flex1,
.box-flex1 {
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex,
.vbox.box-flex,
.box-flex {
  /* Old browsers */
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex2,
.vbox.box-flex2,
.box-flex2 {
  /* Old browsers */
  -webkit-box-flex: 2;
  -moz-box-flex: 2;
  box-flex: 2;
  /* Modern browsers */
  flex: 2;
}
.box-group1 {
  /*  Deprecated */
  -webkit-box-flex-group: 1;
  -moz-box-flex-group: 1;
  box-flex-group: 1;
}
.box-group2 {
  /* Deprecated */
  -webkit-box-flex-group: 2;
  -moz-box-flex-group: 2;
  box-flex-group: 2;
}
.hbox.start,
.vbox.start,
.start {
  /* Old browsers */
  -webkit-box-pack: start;
  -moz-box-pack: start;
  box-pack: start;
  /* Modern browsers */
  justify-content: flex-start;
}
.hbox.end,
.vbox.end,
.end {
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
}
.hbox.center,
.vbox.center,
.center {
  /* Old browsers */
  -webkit-box-pack: center;
  -moz-box-pack: center;
  box-pack: center;
  /* Modern browsers */
  justify-content: center;
}
.hbox.baseline,
.vbox.baseline,
.baseline {
  /* Old browsers */
  -webkit-box-pack: baseline;
  -moz-box-pack: baseline;
  box-pack: baseline;
  /* Modern browsers */
  justify-content: baseline;
}
.hbox.stretch,
.vbox.stretch,
.stretch {
  /* Old browsers */
  -webkit-box-pack: stretch;
  -moz-box-pack: stretch;
  box-pack: stretch;
  /* Modern browsers */
  justify-content: stretch;
}
.hbox.align-start,
.vbox.align-start,
.align-start {
  /* Old browsers */
  -webkit-box-align: start;
  -moz-box-align: start;
  box-align: start;
  /* Modern browsers */
  align-items: flex-start;
}
.hbox.align-end,
.vbox.align-end,
.align-end {
  /* Old browsers */
  -webkit-box-align: end;
  -moz-box-align: end;
  box-align: end;
  /* Modern browsers */
  align-items: flex-end;
}
.hbox.align-center,
.vbox.align-center,
.align-center {
  /* Old browsers */
  -webkit-box-align: center;
  -moz-box-align: center;
  box-align: center;
  /* Modern browsers */
  align-items: center;
}
.hbox.align-baseline,
.vbox.align-baseline,
.align-baseline {
  /* Old browsers */
  -webkit-box-align: baseline;
  -moz-box-align: baseline;
  box-align: baseline;
  /* Modern browsers */
  align-items: baseline;
}
.hbox.align-stretch,
.vbox.align-stretch,
.align-stretch {
  /* Old browsers */
  -webkit-box-align: stretch;
  -moz-box-align: stretch;
  box-align: stretch;
  /* Modern browsers */
  align-items: stretch;
}
div.error {
  margin: 2em;
  text-align: center;
}
div.error > h1 {
  font-size: 500%;
  line-height: normal;
}
div.error > p {
  font-size: 200%;
  line-height: normal;
}
div.traceback-wrapper {
  text-align: left;
  max-width: 800px;
  margin: auto;
}
div.traceback-wrapper pre.traceback {
  max-height: 600px;
  overflow: auto;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
body {
  background-color: #fff;
  /* This makes sure that the body covers the entire window and needs to
       be in a different element than the display: box in wrapper below */
  position: absolute;
  left: 0px;
  right: 0px;
  top: 0px;
  bottom: 0px;
  overflow: visible;
}
body > #header {
  /* Initially hidden to prevent FLOUC */
  display: none;
  background-color: #fff;
  /* Display over codemirror */
  position: relative;
  z-index: 100;
}
body > #header #header-container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  padding: 5px;
  padding-bottom: 5px;
  padding-top: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
body > #header .header-bar {
  width: 100%;
  height: 1px;
  background: #e7e7e7;
  margin-bottom: -1px;
}
@media print {
  body > #header {
    display: none !important;
  }
}
#header-spacer {
  width: 100%;
  visibility: hidden;
}
@media print {
  #header-spacer {
    display: none;
  }
}
#ipython_notebook {
  padding-left: 0px;
  padding-top: 1px;
  padding-bottom: 1px;
}
[dir="rtl"] #ipython_notebook {
  margin-right: 10px;
  margin-left: 0;
}
[dir="rtl"] #ipython_notebook.pull-left {
  float: right !important;
  float: right;
}
.flex-spacer {
  flex: 1;
}
#noscript {
  width: auto;
  padding-top: 16px;
  padding-bottom: 16px;
  text-align: center;
  font-size: 22px;
  color: red;
  font-weight: bold;
}
#ipython_notebook img {
  height: 28px;
}
#site {
  width: 100%;
  display: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  overflow: auto;
}
@media print {
  #site {
    height: auto !important;
  }
}
/* Smaller buttons */
.ui-button .ui-button-text {
  padding: 0.2em 0.8em;
  font-size: 77%;
}
input.ui-button {
  padding: 0.3em 0.9em;
}
span#kernel_logo_widget {
  margin: 0 10px;
}
span#login_widget {
  float: right;
}
[dir="rtl"] span#login_widget {
  float: left;
}
span#login_widget > .button,
#logout {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button:focus,
#logout:focus,
span#login_widget > .button.focus,
#logout.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
span#login_widget > .button:hover,
#logout:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active:hover,
#logout:active:hover,
span#login_widget > .button.active:hover,
#logout.active:hover,
.open > .dropdown-togglespan#login_widget > .button:hover,
.open > .dropdown-toggle#logout:hover,
span#login_widget > .button:active:focus,
#logout:active:focus,
span#login_widget > .button.active:focus,
#logout.active:focus,
.open > .dropdown-togglespan#login_widget > .button:focus,
.open > .dropdown-toggle#logout:focus,
span#login_widget > .button:active.focus,
#logout:active.focus,
span#login_widget > .button.active.focus,
#logout.active.focus,
.open > .dropdown-togglespan#login_widget > .button.focus,
.open > .dropdown-toggle#logout.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  background-image: none;
}
span#login_widget > .button.disabled:hover,
#logout.disabled:hover,
span#login_widget > .button[disabled]:hover,
#logout[disabled]:hover,
fieldset[disabled] span#login_widget > .button:hover,
fieldset[disabled] #logout:hover,
span#login_widget > .button.disabled:focus,
#logout.disabled:focus,
span#login_widget > .button[disabled]:focus,
#logout[disabled]:focus,
fieldset[disabled] span#login_widget > .button:focus,
fieldset[disabled] #logout:focus,
span#login_widget > .button.disabled.focus,
#logout.disabled.focus,
span#login_widget > .button[disabled].focus,
#logout[disabled].focus,
fieldset[disabled] span#login_widget > .button.focus,
fieldset[disabled] #logout.focus {
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button .badge,
#logout .badge {
  color: #fff;
  background-color: #333;
}
.nav-header {
  text-transform: none;
}
#header > span {
  margin-top: 10px;
}
.modal_stretch .modal-dialog {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  min-height: 80vh;
}
.modal_stretch .modal-dialog .modal-body {
  max-height: calc(100vh - 200px);
  overflow: auto;
  flex: 1;
}
.modal-header {
  cursor: move;
}
@media (min-width: 768px) {
  .modal .modal-dialog {
    width: 700px;
  }
}
@media (min-width: 768px) {
  select.form-control {
    margin-left: 12px;
    margin-right: 12px;
  }
}
/*!
*
* IPython auth
*
*/
.center-nav {
  display: inline-block;
  margin-bottom: -4px;
}
[dir="rtl"] .center-nav form.pull-left {
  float: right !important;
  float: right;
}
[dir="rtl"] .center-nav .navbar-text {
  float: right;
}
[dir="rtl"] .navbar-inner {
  text-align: right;
}
[dir="rtl"] div.text-left {
  text-align: right;
}
/*!
*
* IPython tree view
*
*/
/* We need an invisible input field on top of the sentense*/
/* "Drag file onto the list ..." */
.alternate_upload {
  background-color: none;
  display: inline;
}
.alternate_upload.form {
  padding: 0;
  margin: 0;
}
.alternate_upload input.fileinput {
  position: absolute;
  display: block;
  width: 100%;
  height: 100%;
  overflow: hidden;
  cursor: pointer;
  opacity: 0;
  z-index: 2;
}
.alternate_upload .btn-xs > input.fileinput {
  margin: -1px -5px;
}
.alternate_upload .btn-upload {
  position: relative;
  height: 22px;
}
::-webkit-file-upload-button {
  cursor: pointer;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
ul#tabs {
  margin-bottom: 4px;
}
ul#tabs a {
  padding-top: 6px;
  padding-bottom: 4px;
}
[dir="rtl"] ul#tabs.nav-tabs > li {
  float: right;
}
[dir="rtl"] ul#tabs.nav.nav-tabs {
  padding-right: 0;
}
ul.breadcrumb a:focus,
ul.breadcrumb a:hover {
  text-decoration: none;
}
ul.breadcrumb i.icon-home {
  font-size: 16px;
  margin-right: 4px;
}
ul.breadcrumb span {
  color: #5e5e5e;
}
.list_toolbar {
  padding: 4px 0 4px 0;
  vertical-align: middle;
}
.list_toolbar .tree-buttons {
  padding-top: 1px;
}
[dir="rtl"] .list_toolbar .tree-buttons .pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .list_toolbar .col-sm-4,
[dir="rtl"] .list_toolbar .col-sm-8 {
  float: right;
}
.dynamic-buttons {
  padding-top: 3px;
  display: inline-block;
}
.list_toolbar [class*="span"] {
  min-height: 24px;
}
.list_header {
  font-weight: bold;
  background-color: #EEE;
}
.list_placeholder {
  font-weight: bold;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
}
.list_container {
  margin-top: 4px;
  margin-bottom: 20px;
  border: 1px solid #ddd;
  border-radius: 2px;
}
.list_container > div {
  border-bottom: 1px solid #ddd;
}
.list_container > div:hover .list-item {
  background-color: red;
}
.list_container > div:last-child {
  border: none;
}
.list_item:hover .list_item {
  background-color: #ddd;
}
.list_item a {
  text-decoration: none;
}
.list_item:hover {
  background-color: #fafafa;
}
.list_header > div,
.list_item > div {
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
.list_header > div input,
.list_item > div input {
  margin-right: 7px;
  margin-left: 14px;
  vertical-align: text-bottom;
  line-height: 22px;
  position: relative;
  top: -1px;
}
.list_header > div .item_link,
.list_item > div .item_link {
  margin-left: -1px;
  vertical-align: baseline;
  line-height: 22px;
}
[dir="rtl"] .list_item > div input {
  margin-right: 0;
}
.new-file input[type=checkbox] {
  visibility: hidden;
}
.item_name {
  line-height: 22px;
  height: 24px;
}
.item_icon {
  font-size: 14px;
  color: #5e5e5e;
  margin-right: 7px;
  margin-left: 7px;
  line-height: 22px;
  vertical-align: baseline;
}
.item_modified {
  margin-right: 7px;
  margin-left: 7px;
}
[dir="rtl"] .item_modified.pull-right {
  float: left !important;
  float: left;
}
.item_buttons {
  line-height: 1em;
  margin-left: -5px;
}
.item_buttons .btn,
.item_buttons .btn-group,
.item_buttons .input-group {
  float: left;
}
.item_buttons > .btn,
.item_buttons > .btn-group,
.item_buttons > .input-group {
  margin-left: 5px;
}
.item_buttons .btn {
  min-width: 13ex;
}
.item_buttons .running-indicator {
  padding-top: 4px;
  color: #5cb85c;
}
.item_buttons .kernel-name {
  padding-top: 4px;
  color: #5bc0de;
  margin-right: 7px;
  float: left;
}
[dir="rtl"] .item_buttons.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .item_buttons .kernel-name {
  margin-left: 7px;
  float: right;
}
.toolbar_info {
  height: 24px;
  line-height: 24px;
}
.list_item input:not([type=checkbox]) {
  padding-top: 3px;
  padding-bottom: 3px;
  height: 22px;
  line-height: 14px;
  margin: 0px;
}
.highlight_text {
  color: blue;
}
#project_name {
  display: inline-block;
  padding-left: 7px;
  margin-left: -2px;
}
#project_name > .breadcrumb {
  padding: 0px;
  margin-bottom: 0px;
  background-color: transparent;
  font-weight: bold;
}
.sort_button {
  display: inline-block;
  padding-left: 7px;
}
[dir="rtl"] .sort_button.pull-right {
  float: left !important;
  float: left;
}
#tree-selector {
  padding-right: 0px;
}
#button-select-all {
  min-width: 50px;
}
[dir="rtl"] #button-select-all.btn {
  float: right ;
}
#select-all {
  margin-left: 7px;
  margin-right: 2px;
  margin-top: 2px;
  height: 16px;
}
[dir="rtl"] #select-all.pull-left {
  float: right !important;
  float: right;
}
.menu_icon {
  margin-right: 2px;
}
.tab-content .row {
  margin-left: 0px;
  margin-right: 0px;
}
.folder_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f114";
}
.folder_icon:before.fa-pull-left {
  margin-right: .3em;
}
.folder_icon:before.fa-pull-right {
  margin-left: .3em;
}
.folder_icon:before.pull-left {
  margin-right: .3em;
}
.folder_icon:before.pull-right {
  margin-left: .3em;
}
.notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
}
.notebook_icon:before.fa-pull-left {
  margin-right: .3em;
}
.notebook_icon:before.fa-pull-right {
  margin-left: .3em;
}
.notebook_icon:before.pull-left {
  margin-right: .3em;
}
.notebook_icon:before.pull-right {
  margin-left: .3em;
}
.running_notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
  color: #5cb85c;
}
.running_notebook_icon:before.fa-pull-left {
  margin-right: .3em;
}
.running_notebook_icon:before.fa-pull-right {
  margin-left: .3em;
}
.running_notebook_icon:before.pull-left {
  margin-right: .3em;
}
.running_notebook_icon:before.pull-right {
  margin-left: .3em;
}
.file_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f016";
  position: relative;
  top: -2px;
}
.file_icon:before.fa-pull-left {
  margin-right: .3em;
}
.file_icon:before.fa-pull-right {
  margin-left: .3em;
}
.file_icon:before.pull-left {
  margin-right: .3em;
}
.file_icon:before.pull-right {
  margin-left: .3em;
}
#notebook_toolbar .pull-right {
  padding-top: 0px;
  margin-right: -1px;
}
ul#new-menu {
  left: auto;
  right: 0;
}
#new-menu .dropdown-header {
  font-size: 10px;
  border-bottom: 1px solid #e5e5e5;
  padding: 0 0 3px;
  margin: -3px 20px 0;
}
.kernel-menu-icon {
  padding-right: 12px;
  width: 24px;
  content: "\f096";
}
.kernel-menu-icon:before {
  content: "\f096";
}
.kernel-menu-icon-current:before {
  content: "\f00c";
}
#tab_content {
  padding-top: 20px;
}
#running .panel-group .panel {
  margin-top: 3px;
  margin-bottom: 1em;
}
#running .panel-group .panel .panel-heading {
  background-color: #EEE;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
#running .panel-group .panel .panel-heading a:focus,
#running .panel-group .panel .panel-heading a:hover {
  text-decoration: none;
}
#running .panel-group .panel .panel-body {
  padding: 0px;
}
#running .panel-group .panel .panel-body .list_container {
  margin-top: 0px;
  margin-bottom: 0px;
  border: 0px;
  border-radius: 0px;
}
#running .panel-group .panel .panel-body .list_container .list_item {
  border-bottom: 1px solid #ddd;
}
#running .panel-group .panel .panel-body .list_container .list_item:last-child {
  border-bottom: 0px;
}
.delete-button {
  display: none;
}
.duplicate-button {
  display: none;
}
.rename-button {
  display: none;
}
.move-button {
  display: none;
}
.download-button {
  display: none;
}
.shutdown-button {
  display: none;
}
.dynamic-instructions {
  display: inline-block;
  padding-top: 4px;
}
/*!
*
* IPython text editor webapp
*
*/
.selected-keymap i.fa {
  padding: 0px 5px;
}
.selected-keymap i.fa:before {
  content: "\f00c";
}
#mode-menu {
  overflow: auto;
  max-height: 20em;
}
.edit_app #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.edit_app #menubar .navbar {
  /* Use a negative 1 bottom margin, so the border overlaps the border of the
    header */
  margin-bottom: -1px;
}
.dirty-indicator {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator.pull-left {
  margin-right: .3em;
}
.dirty-indicator.pull-right {
  margin-left: .3em;
}
.dirty-indicator-dirty {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-dirty.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-dirty.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-dirty.pull-left {
  margin-right: .3em;
}
.dirty-indicator-dirty.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-clean.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f00c";
}
.dirty-indicator-clean:before.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean:before.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean:before.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean:before.pull-right {
  margin-left: .3em;
}
#filename {
  font-size: 16pt;
  display: table;
  padding: 0px 5px;
}
#current-mode {
  padding-left: 5px;
  padding-right: 5px;
}
#texteditor-backdrop {
  padding-top: 20px;
  padding-bottom: 20px;
}
@media not print {
  #texteditor-backdrop {
    background-color: #EEE;
  }
}
@media print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container {
    padding: 0px;
    background-color: #fff;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
.CodeMirror-dialog {
  background-color: #fff;
}
/*!
*
* IPython notebook
*
*/
/* CSS font colors for translated ANSI escape sequences */
/* The color values are a mix of
   http://www.xcolors.net/dl/baskerville-ivorylight and
   http://www.xcolors.net/dl/euphrasia */
.ansi-black-fg {
  color: #3E424D;
}
.ansi-black-bg {
  background-color: #3E424D;
}
.ansi-black-intense-fg {
  color: #282C36;
}
.ansi-black-intense-bg {
  background-color: #282C36;
}
.ansi-red-fg {
  color: #E75C58;
}
.ansi-red-bg {
  background-color: #E75C58;
}
.ansi-red-intense-fg {
  color: #B22B31;
}
.ansi-red-intense-bg {
  background-color: #B22B31;
}
.ansi-green-fg {
  color: #00A250;
}
.ansi-green-bg {
  background-color: #00A250;
}
.ansi-green-intense-fg {
  color: #007427;
}
.ansi-green-intense-bg {
  background-color: #007427;
}
.ansi-yellow-fg {
  color: #DDB62B;
}
.ansi-yellow-bg {
  background-color: #DDB62B;
}
.ansi-yellow-intense-fg {
  color: #B27D12;
}
.ansi-yellow-intense-bg {
  background-color: #B27D12;
}
.ansi-blue-fg {
  color: #208FFB;
}
.ansi-blue-bg {
  background-color: #208FFB;
}
.ansi-blue-intense-fg {
  color: #0065CA;
}
.ansi-blue-intense-bg {
  background-color: #0065CA;
}
.ansi-magenta-fg {
  color: #D160C4;
}
.ansi-magenta-bg {
  background-color: #D160C4;
}
.ansi-magenta-intense-fg {
  color: #A03196;
}
.ansi-magenta-intense-bg {
  background-color: #A03196;
}
.ansi-cyan-fg {
  color: #60C6C8;
}
.ansi-cyan-bg {
  background-color: #60C6C8;
}
.ansi-cyan-intense-fg {
  color: #258F8F;
}
.ansi-cyan-intense-bg {
  background-color: #258F8F;
}
.ansi-white-fg {
  color: #C5C1B4;
}
.ansi-white-bg {
  background-color: #C5C1B4;
}
.ansi-white-intense-fg {
  color: #A1A6B2;
}
.ansi-white-intense-bg {
  background-color: #A1A6B2;
}
.ansi-default-inverse-fg {
  color: #FFFFFF;
}
.ansi-default-inverse-bg {
  background-color: #000000;
}
.ansi-bold {
  font-weight: bold;
}
.ansi-underline {
  text-decoration: underline;
}
/* The following styles are deprecated an will be removed in a future version */
.ansibold {
  font-weight: bold;
}
.ansi-inverse {
  outline: 0.5px dotted;
}
/* use dark versions for foreground, to improve visibility */
.ansiblack {
  color: black;
}
.ansired {
  color: darkred;
}
.ansigreen {
  color: darkgreen;
}
.ansiyellow {
  color: #c4a000;
}
.ansiblue {
  color: darkblue;
}
.ansipurple {
  color: darkviolet;
}
.ansicyan {
  color: steelblue;
}
.ansigray {
  color: gray;
}
/* and light for background, for the same reason */
.ansibgblack {
  background-color: black;
}
.ansibgred {
  background-color: red;
}
.ansibggreen {
  background-color: green;
}
.ansibgyellow {
  background-color: yellow;
}
.ansibgblue {
  background-color: blue;
}
.ansibgpurple {
  background-color: magenta;
}
.ansibgcyan {
  background-color: cyan;
}
.ansibggray {
  background-color: gray;
}
div.cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  border-radius: 2px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  border-width: 1px;
  border-style: solid;
  border-color: transparent;
  width: 100%;
  padding: 5px;
  /* This acts as a spacer between cells, that is outside the border */
  margin: 0px;
  outline: none;
  position: relative;
  overflow: visible;
}
div.cell:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: transparent;
}
div.cell.jupyter-soft-selected {
  border-left-color: #E3F2FD;
  border-left-width: 1px;
  padding-left: 5px;
  border-right-color: #E3F2FD;
  border-right-width: 1px;
  background: #E3F2FD;
}
@media print {
  div.cell.jupyter-soft-selected {
    border-color: transparent;
  }
}
div.cell.selected,
div.cell.selected.jupyter-soft-selected {
  border-color: #ababab;
}
div.cell.selected:before,
div.cell.selected.jupyter-soft-selected:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: #42A5F5;
}
@media print {
  div.cell.selected,
  div.cell.selected.jupyter-soft-selected {
    border-color: transparent;
  }
}
.edit_mode div.cell.selected {
  border-color: #66BB6A;
}
.edit_mode div.cell.selected:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: #66BB6A;
}
@media print {
  .edit_mode div.cell.selected {
    border-color: transparent;
  }
}
.prompt {
  /* This needs to be wide enough for 3 digit prompt numbers: In[100]: */
  min-width: 14ex;
  /* This padding is tuned to match the padding on the CodeMirror editor. */
  padding: 0.4em;
  margin: 0px;
  font-family: monospace;
  text-align: right;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
  /* Don't highlight prompt number selection */
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  /* Use default cursor */
  cursor: default;
}
@media (max-width: 540px) {
  .prompt {
    text-align: left;
  }
}
div.inner_cell {
  min-width: 0;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_area {
  border: 1px solid #cfcfcf;
  border-radius: 2px;
  background: #f7f7f7;
  line-height: 1.21429em;
}
/* This is needed so that empty prompt areas can collapse to zero height when there
   is no content in the output_subarea and the prompt. The main purpose of this is
   to make sure that empty JavaScript output_subareas have no height. */
div.prompt:empty {
  padding-top: 0;
  padding-bottom: 0;
}
div.unrecognized_cell {
  padding: 5px 5px 5px 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.unrecognized_cell .inner_cell {
  border-radius: 2px;
  padding: 5px;
  font-weight: bold;
  color: red;
  border: 1px solid #cfcfcf;
  background: #eaeaea;
}
div.unrecognized_cell .inner_cell a {
  color: inherit;
  text-decoration: none;
}
div.unrecognized_cell .inner_cell a:hover {
  color: inherit;
  text-decoration: none;
}
@media (max-width: 540px) {
  div.unrecognized_cell > div.prompt {
    display: none;
  }
}
div.code_cell {
  /* avoid page breaking on code cells when printing */
}
@media print {
  div.code_cell {
    page-break-inside: avoid;
  }
}
/* any special styling for code cells that are currently running goes here */
div.input {
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.input {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_prompt {
  color: #303F9F;
  border-top: 1px solid transparent;
}
div.input_area > div.highlight {
  margin: 0.4em;
  border: none;
  padding: 0px;
  background-color: transparent;
}
div.input_area > div.highlight > pre {
  margin: 0px;
  border: none;
  padding: 0px;
  background-color: transparent;
}
/* The following gets added to the <head> if it is detected that the user has a
 * monospace font with inconsistent normal/bold/italic height.  See
 * notebookmain.js.  Such fonts will have keywords vertically offset with
 * respect to the rest of the text.  The user should select a better font.
 * See: https://github.com/ipython/ipython/issues/1503
 *
 * .CodeMirror span {
 *      vertical-align: bottom;
 * }
 */
.CodeMirror {
  line-height: 1.21429em;
  /* Changed from 1em to our global default */
  font-size: 14px;
  height: auto;
  /* Changed to auto to autogrow */
  background: none;
  /* Changed from white to allow our bg to show through */
}
.CodeMirror-scroll {
  /*  The CodeMirror docs are a bit fuzzy on if overflow-y should be hidden or visible.*/
  /*  We have found that if it is visible, vertical scrollbars appear with font size changes.*/
  overflow-y: hidden;
  overflow-x: auto;
}
.CodeMirror-lines {
  /* In CM2, this used to be 0.4em, but in CM3 it went to 4px. We need the em value because */
  /* we have set a different line-height and want this to scale with that. */
  /* Note that this should set vertical padding only, since CodeMirror assumes
       that horizontal padding will be set on CodeMirror pre */
  padding: 0.4em 0;
}
.CodeMirror-linenumber {
  padding: 0 8px 0 4px;
}
.CodeMirror-gutters {
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.CodeMirror pre {
  /* In CM3 this went to 4px from 0 in CM2. This sets horizontal padding only,
    use .CodeMirror-lines for vertical */
  padding: 0 0.4em;
  border: 0;
  border-radius: 0;
}
.CodeMirror-cursor {
  border-left: 1.4px solid black;
}
@media screen and (min-width: 2138px) and (max-width: 4319px) {
  .CodeMirror-cursor {
    border-left: 2px solid black;
  }
}
@media screen and (min-width: 4320px) {
  .CodeMirror-cursor {
    border-left: 4px solid black;
  }
}
/*

Original style from softwaremaniacs.org (c) Ivan Sagalaev <Maniac@SoftwareManiacs.Org>
Adapted from GitHub theme

*/
.highlight-base {
  color: #000;
}
.highlight-variable {
  color: #000;
}
.highlight-variable-2 {
  color: #1a1a1a;
}
.highlight-variable-3 {
  color: #333333;
}
.highlight-string {
  color: #BA2121;
}
.highlight-comment {
  color: #408080;
  font-style: italic;
}
.highlight-number {
  color: #080;
}
.highlight-atom {
  color: #88F;
}
.highlight-keyword {
  color: #008000;
  font-weight: bold;
}
.highlight-builtin {
  color: #008000;
}
.highlight-error {
  color: #f00;
}
.highlight-operator {
  color: #AA22FF;
  font-weight: bold;
}
.highlight-meta {
  color: #AA22FF;
}
/* previously not defined, copying from default codemirror */
.highlight-def {
  color: #00f;
}
.highlight-string-2 {
  color: #f50;
}
.highlight-qualifier {
  color: #555;
}
.highlight-bracket {
  color: #997;
}
.highlight-tag {
  color: #170;
}
.highlight-attribute {
  color: #00c;
}
.highlight-header {
  color: blue;
}
.highlight-quote {
  color: #090;
}
.highlight-link {
  color: #00c;
}
/* apply the same style to codemirror */
.cm-s-ipython span.cm-keyword {
  color: #008000;
  font-weight: bold;
}
.cm-s-ipython span.cm-atom {
  color: #88F;
}
.cm-s-ipython span.cm-number {
  color: #080;
}
.cm-s-ipython span.cm-def {
  color: #00f;
}
.cm-s-ipython span.cm-variable {
  color: #000;
}
.cm-s-ipython span.cm-operator {
  color: #AA22FF;
  font-weight: bold;
}
.cm-s-ipython span.cm-variable-2 {
  color: #1a1a1a;
}
.cm-s-ipython span.cm-variable-3 {
  color: #333333;
}
.cm-s-ipython span.cm-comment {
  color: #408080;
  font-style: italic;
}
.cm-s-ipython span.cm-string {
  color: #BA2121;
}
.cm-s-ipython span.cm-string-2 {
  color: #f50;
}
.cm-s-ipython span.cm-meta {
  color: #AA22FF;
}
.cm-s-ipython span.cm-qualifier {
  color: #555;
}
.cm-s-ipython span.cm-builtin {
  color: #008000;
}
.cm-s-ipython span.cm-bracket {
  color: #997;
}
.cm-s-ipython span.cm-tag {
  color: #170;
}
.cm-s-ipython span.cm-attribute {
  color: #00c;
}
.cm-s-ipython span.cm-header {
  color: blue;
}
.cm-s-ipython span.cm-quote {
  color: #090;
}
.cm-s-ipython span.cm-link {
  color: #00c;
}
.cm-s-ipython span.cm-error {
  color: #f00;
}
.cm-s-ipython span.cm-tab {
  background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAMCAYAAAAkuj5RAAAAAXNSR0IArs4c6QAAAGFJREFUSMft1LsRQFAQheHPowAKoACx3IgEKtaEHujDjORSgWTH/ZOdnZOcM/sgk/kFFWY0qV8foQwS4MKBCS3qR6ixBJvElOobYAtivseIE120FaowJPN75GMu8j/LfMwNjh4HUpwg4LUAAAAASUVORK5CYII=);
  background-position: right;
  background-repeat: no-repeat;
}
div.output_wrapper {
  /* this position must be relative to enable descendents to be absolute within it */
  position: relative;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  z-index: 1;
}
/* class for the output area when it should be height-limited */
div.output_scroll {
  /* ideally, this would be max-height, but FF barfs all over that */
  height: 24em;
  /* FF needs this *and the wrapper* to specify full width, or it will shrinkwrap */
  width: 100%;
  overflow: auto;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  display: block;
}
/* output div while it is collapsed */
div.output_collapsed {
  margin: 0px;
  padding: 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
div.out_prompt_overlay {
  height: 100%;
  padding: 0px 0.4em;
  position: absolute;
  border-radius: 2px;
}
div.out_prompt_overlay:hover {
  /* use inner shadow to get border that is computed the same on WebKit/FF */
  -webkit-box-shadow: inset 0 0 1px #000;
  box-shadow: inset 0 0 1px #000;
  background: rgba(240, 240, 240, 0.5);
}
div.output_prompt {
  color: #D84315;
}
/* This class is the outer container of all output sections. */
div.output_area {
  padding: 0px;
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.output_area .MathJax_Display {
  text-align: left !important;
}
div.output_area .rendered_html table {
  margin-left: 0;
  margin-right: 0;
}
div.output_area .rendered_html img {
  margin-left: 0;
  margin-right: 0;
}
div.output_area img,
div.output_area svg {
  max-width: 100%;
  height: auto;
}
div.output_area img.unconfined,
div.output_area svg.unconfined {
  max-width: none;
}
div.output_area .mglyph > img {
  max-width: none;
}
/* This is needed to protect the pre formating from global settings such
   as that of bootstrap */
.output {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.output_area {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
div.output_area pre {
  margin: 0;
  padding: 1px 0 1px 0;
  border: 0;
  vertical-align: baseline;
  color: black;
  background-color: transparent;
  border-radius: 0;
}
/* This class is for the output subarea inside the output_area and after
   the prompt div. */
div.output_subarea {
  overflow-x: auto;
  padding: 0.4em;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
  max-width: calc(100% - 14ex);
}
div.output_scroll div.output_subarea {
  overflow-x: visible;
}
/* The rest of the output_* classes are for special styling of the different
   output types */
/* all text output has this class: */
div.output_text {
  text-align: left;
  color: #000;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
}
/* stdout/stderr are 'text' as well as 'stream', but execute_result/error are *not* streams */
div.output_stderr {
  background: #fdd;
  /* very light red background for stderr */
}
div.output_latex {
  text-align: left;
}
/* Empty output_javascript divs should have no height */
div.output_javascript:empty {
  padding: 0;
}
.js-error {
  color: darkred;
}
/* raw_input styles */
div.raw_input_container {
  line-height: 1.21429em;
  padding-top: 5px;
}
pre.raw_input_prompt {
  /* nothing needed here. */
}
input.raw_input {
  font-family: monospace;
  font-size: inherit;
  color: inherit;
  width: auto;
  /* make sure input baseline aligns with prompt */
  vertical-align: baseline;
  /* padding + margin = 0.5em between prompt and cursor */
  padding: 0em 0.25em;
  margin: 0em 0.25em;
}
input.raw_input:focus {
  box-shadow: none;
}
p.p-space {
  margin-bottom: 10px;
}
div.output_unrecognized {
  padding: 5px;
  font-weight: bold;
  color: red;
}
div.output_unrecognized a {
  color: inherit;
  text-decoration: none;
}
div.output_unrecognized a:hover {
  color: inherit;
  text-decoration: none;
}
.rendered_html {
  color: #000;
  /* any extras will just be numbers: */
}
.rendered_html em {
  font-style: italic;
}
.rendered_html strong {
  font-weight: bold;
}
.rendered_html u {
  text-decoration: underline;
}
.rendered_html :link {
  text-decoration: underline;
}
.rendered_html :visited {
  text-decoration: underline;
}
.rendered_html h1 {
  font-size: 185.7%;
  margin: 1.08em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h2 {
  font-size: 157.1%;
  margin: 1.27em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h3 {
  font-size: 128.6%;
  margin: 1.55em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h4 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h5 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h6 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h1:first-child {
  margin-top: 0.538em;
}
.rendered_html h2:first-child {
  margin-top: 0.636em;
}
.rendered_html h3:first-child {
  margin-top: 0.777em;
}
.rendered_html h4:first-child {
  margin-top: 1em;
}
.rendered_html h5:first-child {
  margin-top: 1em;
}
.rendered_html h6:first-child {
  margin-top: 1em;
}
.rendered_html ul:not(.list-inline),
.rendered_html ol:not(.list-inline) {
  padding-left: 2em;
}
.rendered_html ul {
  list-style: disc;
}
.rendered_html ul ul {
  list-style: square;
  margin-top: 0;
}
.rendered_html ul ul ul {
  list-style: circle;
}
.rendered_html ol {
  list-style: decimal;
}
.rendered_html ol ol {
  list-style: upper-alpha;
  margin-top: 0;
}
.rendered_html ol ol ol {
  list-style: lower-alpha;
}
.rendered_html ol ol ol ol {
  list-style: lower-roman;
}
.rendered_html ol ol ol ol ol {
  list-style: decimal;
}
.rendered_html * + ul {
  margin-top: 1em;
}
.rendered_html * + ol {
  margin-top: 1em;
}
.rendered_html hr {
  color: black;
  background-color: black;
}
.rendered_html pre {
  margin: 1em 2em;
  padding: 0px;
  background-color: #fff;
}
.rendered_html code {
  background-color: #eff0f1;
}
.rendered_html p code {
  padding: 1px 5px;
}
.rendered_html pre code {
  background-color: #fff;
}
.rendered_html pre,
.rendered_html code {
  border: 0;
  color: #000;
  font-size: 100%;
}
.rendered_html blockquote {
  margin: 1em 2em;
}
.rendered_html table {
  margin-left: auto;
  margin-right: auto;
  border: none;
  border-collapse: collapse;
  border-spacing: 0;
  color: black;
  font-size: 12px;
  table-layout: fixed;
}
.rendered_html thead {
  border-bottom: 1px solid black;
  vertical-align: bottom;
}
.rendered_html tr,
.rendered_html th,
.rendered_html td {
  text-align: right;
  vertical-align: middle;
  padding: 0.5em 0.5em;
  line-height: normal;
  white-space: normal;
  max-width: none;
  border: none;
}
.rendered_html th {
  font-weight: bold;
}
.rendered_html tbody tr:nth-child(odd) {
  background: #f5f5f5;
}
.rendered_html tbody tr:hover {
  background: rgba(66, 165, 245, 0.2);
}
.rendered_html * + table {
  margin-top: 1em;
}
.rendered_html p {
  text-align: left;
}
.rendered_html * + p {
  margin-top: 1em;
}
.rendered_html img {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.rendered_html * + img {
  margin-top: 1em;
}
.rendered_html img,
.rendered_html svg {
  max-width: 100%;
  height: auto;
}
.rendered_html img.unconfined,
.rendered_html svg.unconfined {
  max-width: none;
}
.rendered_html .alert {
  margin-bottom: initial;
}
.rendered_html * + .alert {
  margin-top: 1em;
}
[dir="rtl"] .rendered_html p {
  text-align: right;
}
div.text_cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.text_cell > div.prompt {
    display: none;
  }
}
div.text_cell_render {
  /*font-family: "Helvetica Neue", Arial, Helvetica, Geneva, sans-serif;*/
  outline: none;
  resize: none;
  width: inherit;
  border-style: none;
  padding: 0.5em 0.5em 0.5em 0.4em;
  color: #000;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
a.anchor-link:link {
  text-decoration: none;
  padding: 0px 20px;
  visibility: hidden;
}
h1:hover .anchor-link,
h2:hover .anchor-link,
h3:hover .anchor-link,
h4:hover .anchor-link,
h5:hover .anchor-link,
h6:hover .anchor-link {
  visibility: visible;
}
.text_cell.rendered .input_area {
  display: none;
}
.text_cell.rendered .rendered_html {
  overflow-x: auto;
  overflow-y: hidden;
}
.text_cell.rendered .rendered_html tr,
.text_cell.rendered .rendered_html th,
.text_cell.rendered .rendered_html td {
  max-width: none;
}
.text_cell.unrendered .text_cell_render {
  display: none;
}
.text_cell .dropzone .input_area {
  border: 2px dashed #bababa;
  margin: -1px;
}
.cm-header-1,
.cm-header-2,
.cm-header-3,
.cm-header-4,
.cm-header-5,
.cm-header-6 {
  font-weight: bold;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
}
.cm-header-1 {
  font-size: 185.7%;
}
.cm-header-2 {
  font-size: 157.1%;
}
.cm-header-3 {
  font-size: 128.6%;
}
.cm-header-4 {
  font-size: 110%;
}
.cm-header-5 {
  font-size: 100%;
  font-style: italic;
}
.cm-header-6 {
  font-size: 100%;
  font-style: italic;
}
/*!
*
* IPython notebook webapp
*
*/
@media (max-width: 767px) {
  .notebook_app {
    padding-left: 0px;
    padding-right: 0px;
  }
}
#ipython-main-app {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook_panel {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook {
  font-size: 14px;
  line-height: 20px;
  overflow-y: hidden;
  overflow-x: auto;
  width: 100%;
  /* This spaces the page away from the edge of the notebook area */
  padding-top: 20px;
  margin: 0px;
  outline: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  min-height: 100%;
}
@media not print {
  #notebook-container {
    padding: 15px;
    background-color: #fff;
    min-height: 0;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
@media print {
  #notebook-container {
    width: 100%;
  }
}
div.ui-widget-content {
  border: 1px solid #ababab;
  outline: none;
}
pre.dialog {
  background-color: #f7f7f7;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0.4em;
  padding-left: 2em;
}
p.dialog {
  padding: 0.2em;
}
/* Word-wrap output correctly.  This is the CSS3 spelling, though Firefox seems
   to not honor it correctly.  Webkit browsers (Chrome, rekonq, Safari) do.
 */
pre,
code,
kbd,
samp {
  white-space: pre-wrap;
}
#fonttest {
  font-family: monospace;
}
p {
  margin-bottom: 0;
}
.end_space {
  min-height: 100px;
  transition: height .2s ease;
}
.notebook_app > #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
@media not print {
  .notebook_app {
    background-color: #EEE;
  }
}
kbd {
  border-style: solid;
  border-width: 1px;
  box-shadow: none;
  margin: 2px;
  padding-left: 2px;
  padding-right: 2px;
  padding-top: 1px;
  padding-bottom: 1px;
}
.jupyter-keybindings {
  padding: 1px;
  line-height: 24px;
  border-bottom: 1px solid gray;
}
.jupyter-keybindings input {
  margin: 0;
  padding: 0;
  border: none;
}
.jupyter-keybindings i {
  padding: 6px;
}
.well code {
  background-color: #ffffff;
  border-color: #ababab;
  border-width: 1px;
  border-style: solid;
  padding: 2px;
  padding-top: 1px;
  padding-bottom: 1px;
}
/* CSS for the cell toolbar */
.celltoolbar {
  border: thin solid #CFCFCF;
  border-bottom: none;
  background: #EEE;
  border-radius: 2px 2px 0px 0px;
  width: 100%;
  height: 29px;
  padding-right: 4px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
  display: -webkit-flex;
}
@media print {
  .celltoolbar {
    display: none;
  }
}
.ctb_hideshow {
  display: none;
  vertical-align: bottom;
}
/* ctb_show is added to the ctb_hideshow div to show the cell toolbar.
   Cell toolbars are only shown when the ctb_global_show class is also set.
*/
.ctb_global_show .ctb_show.ctb_hideshow {
  display: block;
}
.ctb_global_show .ctb_show + .input_area,
.ctb_global_show .ctb_show + div.text_cell_input,
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border-top-right-radius: 0px;
  border-top-left-radius: 0px;
}
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border: 1px solid #cfcfcf;
}
.celltoolbar {
  font-size: 87%;
  padding-top: 3px;
}
.celltoolbar select {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
  width: inherit;
  font-size: inherit;
  height: 22px;
  padding: 0px;
  display: inline-block;
}
.celltoolbar select:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.celltoolbar select::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.celltoolbar select:-ms-input-placeholder {
  color: #999;
}
.celltoolbar select::-webkit-input-placeholder {
  color: #999;
}
.celltoolbar select::-ms-expand {
  border: 0;
  background-color: transparent;
}
.celltoolbar select[disabled],
.celltoolbar select[readonly],
fieldset[disabled] .celltoolbar select {
  background-color: #eeeeee;
  opacity: 1;
}
.celltoolbar select[disabled],
fieldset[disabled] .celltoolbar select {
  cursor: not-allowed;
}
textarea.celltoolbar select {
  height: auto;
}
select.celltoolbar select {
  height: 30px;
  line-height: 30px;
}
textarea.celltoolbar select,
select[multiple].celltoolbar select {
  height: auto;
}
.celltoolbar label {
  margin-left: 5px;
  margin-right: 5px;
}
.tags_button_container {
  width: 100%;
  display: flex;
}
.tag-container {
  display: flex;
  flex-direction: row;
  flex-grow: 1;
  overflow: hidden;
  position: relative;
}
.tag-container > * {
  margin: 0 4px;
}
.remove-tag-btn {
  margin-left: 4px;
}
.tags-input {
  display: flex;
}
.cell-tag:last-child:after {
  content: "";
  position: absolute;
  right: 0;
  width: 40px;
  height: 100%;
  /* Fade to background color of cell toolbar */
  background: linear-gradient(to right, rgba(0, 0, 0, 0), #EEE);
}
.tags-input > * {
  margin-left: 4px;
}
.cell-tag,
.tags-input input,
.tags-input button {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
  box-shadow: none;
  width: inherit;
  font-size: inherit;
  height: 22px;
  line-height: 22px;
  padding: 0px 4px;
  display: inline-block;
}
.cell-tag:focus,
.tags-input input:focus,
.tags-input button:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.cell-tag::-moz-placeholder,
.tags-input input::-moz-placeholder,
.tags-input button::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.cell-tag:-ms-input-placeholder,
.tags-input input:-ms-input-placeholder,
.tags-input button:-ms-input-placeholder {
  color: #999;
}
.cell-tag::-webkit-input-placeholder,
.tags-input input::-webkit-input-placeholder,
.tags-input button::-webkit-input-placeholder {
  color: #999;
}
.cell-tag::-ms-expand,
.tags-input input::-ms-expand,
.tags-input button::-ms-expand {
  border: 0;
  background-color: transparent;
}
.cell-tag[disabled],
.tags-input input[disabled],
.tags-input button[disabled],
.cell-tag[readonly],
.tags-input input[readonly],
.tags-input button[readonly],
fieldset[disabled] .cell-tag,
fieldset[disabled] .tags-input input,
fieldset[disabled] .tags-input button {
  background-color: #eeeeee;
  opacity: 1;
}
.cell-tag[disabled],
.tags-input input[disabled],
.tags-input button[disabled],
fieldset[disabled] .cell-tag,
fieldset[disabled] .tags-input input,
fieldset[disabled] .tags-input button {
  cursor: not-allowed;
}
textarea.cell-tag,
textarea.tags-input input,
textarea.tags-input button {
  height: auto;
}
select.cell-tag,
select.tags-input input,
select.tags-input button {
  height: 30px;
  line-height: 30px;
}
textarea.cell-tag,
textarea.tags-input input,
textarea.tags-input button,
select[multiple].cell-tag,
select[multiple].tags-input input,
select[multiple].tags-input button {
  height: auto;
}
.cell-tag,
.tags-input button {
  padding: 0px 4px;
}
.cell-tag {
  background-color: #fff;
  white-space: nowrap;
}
.tags-input input[type=text]:focus {
  outline: none;
  box-shadow: none;
  border-color: #ccc;
}
.completions {
  position: absolute;
  z-index: 110;
  overflow: hidden;
  border: 1px solid #ababab;
  border-radius: 2px;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  line-height: 1;
}
.completions select {
  background: white;
  outline: none;
  border: none;
  padding: 0px;
  margin: 0px;
  overflow: auto;
  font-family: monospace;
  font-size: 110%;
  color: #000;
  width: auto;
}
.completions select option.context {
  color: #286090;
}
#kernel_logo_widget .current_kernel_logo {
  display: none;
  margin-top: -1px;
  margin-bottom: -1px;
  width: 32px;
  height: 32px;
}
[dir="rtl"] #kernel_logo_widget {
  float: left !important;
  float: left;
}
.modal .modal-body .move-path {
  display: flex;
  flex-direction: row;
  justify-content: space;
  align-items: center;
}
.modal .modal-body .move-path .server-root {
  padding-right: 20px;
}
.modal .modal-body .move-path .path-input {
  flex: 1;
}
#menubar {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  margin-top: 1px;
}
#menubar .navbar {
  border-top: 1px;
  border-radius: 0px 0px 2px 2px;
  margin-bottom: 0px;
}
#menubar .navbar-toggle {
  float: left;
  padding-top: 7px;
  padding-bottom: 7px;
  border: none;
}
#menubar .navbar-collapse {
  clear: left;
}
[dir="rtl"] #menubar .navbar-toggle {
  float: right;
}
[dir="rtl"] #menubar .navbar-collapse {
  clear: right;
}
[dir="rtl"] #menubar .navbar-nav {
  float: right;
}
[dir="rtl"] #menubar .nav {
  padding-right: 0px;
}
[dir="rtl"] #menubar .navbar-nav > li {
  float: right;
}
[dir="rtl"] #menubar .navbar-right {
  float: left !important;
}
[dir="rtl"] ul.dropdown-menu {
  text-align: right;
  left: auto;
}
[dir="rtl"] ul#new-menu.dropdown-menu {
  right: auto;
  left: 0;
}
.nav-wrapper {
  border-bottom: 1px solid #e7e7e7;
}
i.menu-icon {
  padding-top: 4px;
}
[dir="rtl"] i.menu-icon.pull-right {
  float: left !important;
  float: left;
}
ul#help_menu li a {
  overflow: hidden;
  padding-right: 2.2em;
}
ul#help_menu li a i {
  margin-right: -1.2em;
}
[dir="rtl"] ul#help_menu li a {
  padding-left: 2.2em;
}
[dir="rtl"] ul#help_menu li a i {
  margin-right: 0;
  margin-left: -1.2em;
}
[dir="rtl"] ul#help_menu li a i.pull-right {
  float: left !important;
  float: left;
}
.dropdown-submenu {
  position: relative;
}
.dropdown-submenu > .dropdown-menu {
  top: 0;
  left: 100%;
  margin-top: -6px;
  margin-left: -1px;
}
[dir="rtl"] .dropdown-submenu > .dropdown-menu {
  right: 100%;
  margin-right: -1px;
}
.dropdown-submenu:hover > .dropdown-menu {
  display: block;
}
.dropdown-submenu > a:after {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: block;
  content: "\f0da";
  float: right;
  color: #333333;
  margin-top: 2px;
  margin-right: -10px;
}
.dropdown-submenu > a:after.fa-pull-left {
  margin-right: .3em;
}
.dropdown-submenu > a:after.fa-pull-right {
  margin-left: .3em;
}
.dropdown-submenu > a:after.pull-left {
  margin-right: .3em;
}
.dropdown-submenu > a:after.pull-right {
  margin-left: .3em;
}
[dir="rtl"] .dropdown-submenu > a:after {
  float: left;
  content: "\f0d9";
  margin-right: 0;
  margin-left: -10px;
}
.dropdown-submenu:hover > a:after {
  color: #262626;
}
.dropdown-submenu.pull-left {
  float: none;
}
.dropdown-submenu.pull-left > .dropdown-menu {
  left: -100%;
  margin-left: 10px;
}
#notification_area {
  float: right !important;
  float: right;
  z-index: 10;
}
[dir="rtl"] #notification_area {
  float: left !important;
  float: left;
}
.indicator_area {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
[dir="rtl"] .indicator_area {
  float: left !important;
  float: left;
}
#kernel_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  border-left: 1px solid;
}
#kernel_indicator .kernel_indicator_name {
  padding-left: 5px;
  padding-right: 5px;
}
[dir="rtl"] #kernel_indicator {
  float: left !important;
  float: left;
  border-left: 0;
  border-right: 1px solid;
}
#modal_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
[dir="rtl"] #modal_indicator {
  float: left !important;
  float: left;
}
#readonly-indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  margin-top: 2px;
  margin-bottom: 0px;
  margin-left: 0px;
  margin-right: 0px;
  display: none;
}
.modal_indicator:before {
  width: 1.28571429em;
  text-align: center;
}
.edit_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f040";
}
.edit_mode .modal_indicator:before.fa-pull-left {
  margin-right: .3em;
}
.edit_mode .modal_indicator:before.fa-pull-right {
  margin-left: .3em;
}
.edit_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.edit_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.command_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: ' ';
}
.command_mode .modal_indicator:before.fa-pull-left {
  margin-right: .3em;
}
.command_mode .modal_indicator:before.fa-pull-right {
  margin-left: .3em;
}
.command_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.command_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.kernel_idle_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f10c";
}
.kernel_idle_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_idle_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_idle_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_idle_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_busy_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f111";
}
.kernel_busy_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_busy_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_busy_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_busy_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_dead_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f1e2";
}
.kernel_dead_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_dead_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_dead_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_dead_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_disconnected_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f127";
}
.kernel_disconnected_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_disconnected_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_disconnected_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_disconnected_icon:before.pull-right {
  margin-left: .3em;
}
.notification_widget {
  color: #777;
  z-index: 10;
  background: rgba(240, 240, 240, 0.5);
  margin-right: 4px;
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget:focus,
.notification_widget.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.notification_widget:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active:hover,
.notification_widget.active:hover,
.open > .dropdown-toggle.notification_widget:hover,
.notification_widget:active:focus,
.notification_widget.active:focus,
.open > .dropdown-toggle.notification_widget:focus,
.notification_widget:active.focus,
.notification_widget.active.focus,
.open > .dropdown-toggle.notification_widget.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  background-image: none;
}
.notification_widget.disabled:hover,
.notification_widget[disabled]:hover,
fieldset[disabled] .notification_widget:hover,
.notification_widget.disabled:focus,
.notification_widget[disabled]:focus,
fieldset[disabled] .notification_widget:focus,
.notification_widget.disabled.focus,
.notification_widget[disabled].focus,
fieldset[disabled] .notification_widget.focus {
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget .badge {
  color: #fff;
  background-color: #333;
}
.notification_widget.warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning:focus,
.notification_widget.warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.notification_widget.warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active:hover,
.notification_widget.warning.active:hover,
.open > .dropdown-toggle.notification_widget.warning:hover,
.notification_widget.warning:active:focus,
.notification_widget.warning.active:focus,
.open > .dropdown-toggle.notification_widget.warning:focus,
.notification_widget.warning:active.focus,
.notification_widget.warning.active.focus,
.open > .dropdown-toggle.notification_widget.warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  background-image: none;
}
.notification_widget.warning.disabled:hover,
.notification_widget.warning[disabled]:hover,
fieldset[disabled] .notification_widget.warning:hover,
.notification_widget.warning.disabled:focus,
.notification_widget.warning[disabled]:focus,
fieldset[disabled] .notification_widget.warning:focus,
.notification_widget.warning.disabled.focus,
.notification_widget.warning[disabled].focus,
fieldset[disabled] .notification_widget.warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.notification_widget.success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success:focus,
.notification_widget.success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.notification_widget.success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active:hover,
.notification_widget.success.active:hover,
.open > .dropdown-toggle.notification_widget.success:hover,
.notification_widget.success:active:focus,
.notification_widget.success.active:focus,
.open > .dropdown-toggle.notification_widget.success:focus,
.notification_widget.success:active.focus,
.notification_widget.success.active.focus,
.open > .dropdown-toggle.notification_widget.success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  background-image: none;
}
.notification_widget.success.disabled:hover,
.notification_widget.success[disabled]:hover,
fieldset[disabled] .notification_widget.success:hover,
.notification_widget.success.disabled:focus,
.notification_widget.success[disabled]:focus,
fieldset[disabled] .notification_widget.success:focus,
.notification_widget.success.disabled.focus,
.notification_widget.success[disabled].focus,
fieldset[disabled] .notification_widget.success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.notification_widget.info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info:focus,
.notification_widget.info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.notification_widget.info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active:hover,
.notification_widget.info.active:hover,
.open > .dropdown-toggle.notification_widget.info:hover,
.notification_widget.info:active:focus,
.notification_widget.info.active:focus,
.open > .dropdown-toggle.notification_widget.info:focus,
.notification_widget.info:active.focus,
.notification_widget.info.active.focus,
.open > .dropdown-toggle.notification_widget.info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  background-image: none;
}
.notification_widget.info.disabled:hover,
.notification_widget.info[disabled]:hover,
fieldset[disabled] .notification_widget.info:hover,
.notification_widget.info.disabled:focus,
.notification_widget.info[disabled]:focus,
fieldset[disabled] .notification_widget.info:focus,
.notification_widget.info.disabled.focus,
.notification_widget.info[disabled].focus,
fieldset[disabled] .notification_widget.info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.notification_widget.danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger:focus,
.notification_widget.danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.notification_widget.danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active:hover,
.notification_widget.danger.active:hover,
.open > .dropdown-toggle.notification_widget.danger:hover,
.notification_widget.danger:active:focus,
.notification_widget.danger.active:focus,
.open > .dropdown-toggle.notification_widget.danger:focus,
.notification_widget.danger:active.focus,
.notification_widget.danger.active.focus,
.open > .dropdown-toggle.notification_widget.danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  background-image: none;
}
.notification_widget.danger.disabled:hover,
.notification_widget.danger[disabled]:hover,
fieldset[disabled] .notification_widget.danger:hover,
.notification_widget.danger.disabled:focus,
.notification_widget.danger[disabled]:focus,
fieldset[disabled] .notification_widget.danger:focus,
.notification_widget.danger.disabled.focus,
.notification_widget.danger[disabled].focus,
fieldset[disabled] .notification_widget.danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger .badge {
  color: #d9534f;
  background-color: #fff;
}
div#pager {
  background-color: #fff;
  font-size: 14px;
  line-height: 20px;
  overflow: hidden;
  display: none;
  position: fixed;
  bottom: 0px;
  width: 100%;
  max-height: 50%;
  padding-top: 8px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  /* Display over codemirror */
  z-index: 100;
  /* Hack which prevents jquery ui resizable from changing top. */
  top: auto !important;
}
div#pager pre {
  line-height: 1.21429em;
  color: #000;
  background-color: #f7f7f7;
  padding: 0.4em;
}
div#pager #pager-button-area {
  position: absolute;
  top: 8px;
  right: 20px;
}
div#pager #pager-contents {
  position: relative;
  overflow: auto;
  width: 100%;
  height: 100%;
}
div#pager #pager-contents #pager-container {
  position: relative;
  padding: 15px 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
div#pager .ui-resizable-handle {
  top: 0px;
  height: 8px;
  background: #f7f7f7;
  border-top: 1px solid #cfcfcf;
  border-bottom: 1px solid #cfcfcf;
  /* This injects handle bars (a short, wide = symbol) for 
        the resize handle. */
}
div#pager .ui-resizable-handle::after {
  content: '';
  top: 2px;
  left: 50%;
  height: 3px;
  width: 30px;
  margin-left: -15px;
  position: absolute;
  border-top: 1px solid #cfcfcf;
}
.quickhelp {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  line-height: 1.8em;
}
.shortcut_key {
  display: inline-block;
  width: 21ex;
  text-align: right;
  font-family: monospace;
}
.shortcut_descr {
  display: inline-block;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
span.save_widget {
  height: 30px;
  margin-top: 4px;
  display: flex;
  justify-content: flex-start;
  align-items: baseline;
  width: 50%;
  flex: 1;
}
span.save_widget span.filename {
  height: 100%;
  line-height: 1em;
  margin-left: 16px;
  border: none;
  font-size: 146.5%;
  text-overflow: ellipsis;
  overflow: hidden;
  white-space: nowrap;
  border-radius: 2px;
}
span.save_widget span.filename:hover {
  background-color: #e6e6e6;
}
[dir="rtl"] span.save_widget.pull-left {
  float: right !important;
  float: right;
}
[dir="rtl"] span.save_widget span.filename {
  margin-left: 0;
  margin-right: 16px;
}
span.checkpoint_status,
span.autosave_status {
  font-size: small;
  white-space: nowrap;
  padding: 0 5px;
}
@media (max-width: 767px) {
  span.save_widget {
    font-size: small;
    padding: 0 0 0 5px;
  }
  span.checkpoint_status,
  span.autosave_status {
    display: none;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  span.checkpoint_status {
    display: none;
  }
  span.autosave_status {
    font-size: x-small;
  }
}
.toolbar {
  padding: 0px;
  margin-left: -5px;
  margin-top: 2px;
  margin-bottom: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.toolbar select,
.toolbar label {
  width: auto;
  vertical-align: middle;
  margin-right: 2px;
  margin-bottom: 0px;
  display: inline;
  font-size: 92%;
  margin-left: 0.3em;
  margin-right: 0.3em;
  padding: 0px;
  padding-top: 3px;
}
.toolbar .btn {
  padding: 2px 8px;
}
.toolbar .btn-group {
  margin-top: 0px;
  margin-left: 5px;
}
.toolbar-btn-label {
  margin-left: 6px;
}
#maintoolbar {
  margin-bottom: -3px;
  margin-top: -8px;
  border: 0px;
  min-height: 27px;
  margin-left: 0px;
  padding-top: 11px;
  padding-bottom: 3px;
}
#maintoolbar .navbar-text {
  float: none;
  vertical-align: middle;
  text-align: right;
  margin-left: 5px;
  margin-right: 0px;
  margin-top: 0px;
}
.select-xs {
  height: 24px;
}
[dir="rtl"] .btn-group > .btn,
.btn-group-vertical > .btn {
  float: right;
}
.pulse,
.dropdown-menu > li > a.pulse,
li.pulse > a.dropdown-toggle,
li.pulse.open > a.dropdown-toggle {
  background-color: #F37626;
  color: white;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
/** WARNING IF YOU ARE EDITTING THIS FILE, if this is a .css file, It has a lot
 * of chance of beeing generated from the ../less/[samename].less file, you can
 * try to get back the less file by reverting somme commit in history
 **/
/*
 * We'll try to get something pretty, so we
 * have some strange css to have the scroll bar on
 * the left with fix button on the top right of the tooltip
 */
@-moz-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-webkit-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-moz-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
@-webkit-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
/*properties of tooltip after "expand"*/
.bigtooltip {
  overflow: auto;
  height: 200px;
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
}
/*properties of tooltip before "expand"*/
.smalltooltip {
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
  text-overflow: ellipsis;
  overflow: hidden;
  height: 80px;
}
.tooltipbuttons {
  position: absolute;
  padding-right: 15px;
  top: 0px;
  right: 0px;
}
.tooltiptext {
  /*avoid the button to overlap on some docstring*/
  padding-right: 30px;
}
.ipython_tooltip {
  max-width: 700px;
  /*fade-in animation when inserted*/
  -webkit-animation: fadeOut 400ms;
  -moz-animation: fadeOut 400ms;
  animation: fadeOut 400ms;
  -webkit-animation: fadeIn 400ms;
  -moz-animation: fadeIn 400ms;
  animation: fadeIn 400ms;
  vertical-align: middle;
  background-color: #f7f7f7;
  overflow: visible;
  border: #ababab 1px solid;
  outline: none;
  padding: 3px;
  margin: 0px;
  padding-left: 7px;
  font-family: monospace;
  min-height: 50px;
  -moz-box-shadow: 0px 6px 10px -1px #adadad;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  border-radius: 2px;
  position: absolute;
  z-index: 1000;
}
.ipython_tooltip a {
  float: right;
}
.ipython_tooltip .tooltiptext pre {
  border: 0;
  border-radius: 0;
  font-size: 100%;
  background-color: #f7f7f7;
}
.pretooltiparrow {
  left: 0px;
  margin: 0px;
  top: -16px;
  width: 40px;
  height: 16px;
  overflow: hidden;
  position: absolute;
}
.pretooltiparrow:before {
  background-color: #f7f7f7;
  border: 1px #ababab solid;
  z-index: 11;
  content: "";
  position: absolute;
  left: 15px;
  top: 10px;
  width: 25px;
  height: 25px;
  -webkit-transform: rotate(45deg);
  -moz-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  -o-transform: rotate(45deg);
}
ul.typeahead-list i {
  margin-left: -10px;
  width: 18px;
}
[dir="rtl"] ul.typeahead-list i {
  margin-left: 0;
  margin-right: -10px;
}
ul.typeahead-list {
  max-height: 80vh;
  overflow: auto;
}
ul.typeahead-list > li > a {
  /** Firefox bug **/
  /* see https://github.com/jupyter/notebook/issues/559 */
  white-space: normal;
}
ul.typeahead-list  > li > a.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .typeahead-list {
  text-align: right;
}
.cmd-palette .modal-body {
  padding: 7px;
}
.cmd-palette form {
  background: white;
}
.cmd-palette input {
  outline: none;
}
.no-shortcut {
  min-width: 20px;
  color: transparent;
}
[dir="rtl"] .no-shortcut.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .command-shortcut.pull-right {
  float: left !important;
  float: left;
}
.command-shortcut:before {
  content: "(command mode)";
  padding-right: 3px;
  color: #777777;
}
.edit-shortcut:before {
  content: "(edit)";
  padding-right: 3px;
  color: #777777;
}
[dir="rtl"] .edit-shortcut.pull-right {
  float: left !important;
  float: left;
}
#find-and-replace #replace-preview .match,
#find-and-replace #replace-preview .insert {
  background-color: #BBDEFB;
  border-color: #90CAF9;
  border-style: solid;
  border-width: 1px;
  border-radius: 0px;
}
[dir="ltr"] #find-and-replace .input-group-btn + .form-control {
  border-left: none;
}
[dir="rtl"] #find-and-replace .input-group-btn + .form-control {
  border-right: none;
}
#find-and-replace #replace-preview .replace .match {
  background-color: #FFCDD2;
  border-color: #EF9A9A;
  border-radius: 0px;
}
#find-and-replace #replace-preview .replace .insert {
  background-color: #C8E6C9;
  border-color: #A5D6A7;
  border-radius: 0px;
}
#find-and-replace #replace-preview {
  max-height: 60vh;
  overflow: auto;
}
#find-and-replace #replace-preview pre {
  padding: 5px 10px;
}
.terminal-app {
  background: #EEE;
}
.terminal-app #header {
  background: #fff;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.terminal-app .terminal {
  width: 100%;
  float: left;
  font-family: monospace;
  color: white;
  background: black;
  padding: 0.4em;
  border-radius: 2px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
}
.terminal-app .terminal,
.terminal-app .terminal dummy-screen {
  line-height: 1em;
  font-size: 14px;
}
.terminal-app .terminal .xterm-rows {
  padding: 10px;
}
.terminal-app .terminal-cursor {
  color: black;
  background: white;
}
.terminal-app #terminado-container {
  margin-top: 20px;
}
/*# sourceMappingURL=style.min.css.map */
    </style>
<style type="text/css">
    .highlight .hll { background-color: #ffffcc }
.highlight  { background: #f8f8f8; }
.highlight .c { color: #408080; font-style: italic } /* Comment */
.highlight .err { border: 1px solid #FF0000 } /* Error */
.highlight .k { color: #008000; font-weight: bold } /* Keyword */
.highlight .o { color: #666666 } /* Operator */
.highlight .ch { color: #408080; font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: #408080; font-style: italic } /* Comment.Multiline */
.highlight .cp { color: #BC7A00 } /* Comment.Preproc */
.highlight .cpf { color: #408080; font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: #408080; font-style: italic } /* Comment.Single */
.highlight .cs { color: #408080; font-style: italic } /* Comment.Special */
.highlight .gd { color: #A00000 } /* Generic.Deleted */
.highlight .ge { font-style: italic } /* Generic.Emph */
.highlight .gr { color: #FF0000 } /* Generic.Error */
.highlight .gh { color: #000080; font-weight: bold } /* Generic.Heading */
.highlight .gi { color: #00A000 } /* Generic.Inserted */
.highlight .go { color: #888888 } /* Generic.Output */
.highlight .gp { color: #000080; font-weight: bold } /* Generic.Prompt */
.highlight .gs { font-weight: bold } /* Generic.Strong */
.highlight .gu { color: #800080; font-weight: bold } /* Generic.Subheading */
.highlight .gt { color: #0044DD } /* Generic.Traceback */
.highlight .kc { color: #008000; font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: #008000; font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: #008000; font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: #008000 } /* Keyword.Pseudo */
.highlight .kr { color: #008000; font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: #B00040 } /* Keyword.Type */
.highlight .m { color: #666666 } /* Literal.Number */
.highlight .s { color: #BA2121 } /* Literal.String */
.highlight .na { color: #7D9029 } /* Name.Attribute */
.highlight .nb { color: #008000 } /* Name.Builtin */
.highlight .nc { color: #0000FF; font-weight: bold } /* Name.Class */
.highlight .no { color: #880000 } /* Name.Constant */
.highlight .nd { color: #AA22FF } /* Name.Decorator */
.highlight .ni { color: #999999; font-weight: bold } /* Name.Entity */
.highlight .ne { color: #D2413A; font-weight: bold } /* Name.Exception */
.highlight .nf { color: #0000FF } /* Name.Function */
.highlight .nl { color: #A0A000 } /* Name.Label */
.highlight .nn { color: #0000FF; font-weight: bold } /* Name.Namespace */
.highlight .nt { color: #008000; font-weight: bold } /* Name.Tag */
.highlight .nv { color: #19177C } /* Name.Variable */
.highlight .ow { color: #AA22FF; font-weight: bold } /* Operator.Word */
.highlight .w { color: #bbbbbb } /* Text.Whitespace */
.highlight .mb { color: #666666 } /* Literal.Number.Bin */
.highlight .mf { color: #666666 } /* Literal.Number.Float */
.highlight .mh { color: #666666 } /* Literal.Number.Hex */
.highlight .mi { color: #666666 } /* Literal.Number.Integer */
.highlight .mo { color: #666666 } /* Literal.Number.Oct */
.highlight .sa { color: #BA2121 } /* Literal.String.Affix */
.highlight .sb { color: #BA2121 } /* Literal.String.Backtick */
.highlight .sc { color: #BA2121 } /* Literal.String.Char */
.highlight .dl { color: #BA2121 } /* Literal.String.Delimiter */
.highlight .sd { color: #BA2121; font-style: italic } /* Literal.String.Doc */
.highlight .s2 { color: #BA2121 } /* Literal.String.Double */
.highlight .se { color: #BB6622; font-weight: bold } /* Literal.String.Escape */
.highlight .sh { color: #BA2121 } /* Literal.String.Heredoc */
.highlight .si { color: #BB6688; font-weight: bold } /* Literal.String.Interpol */
.highlight .sx { color: #008000 } /* Literal.String.Other */
.highlight .sr { color: #BB6688 } /* Literal.String.Regex */
.highlight .s1 { color: #BA2121 } /* Literal.String.Single */
.highlight .ss { color: #19177C } /* Literal.String.Symbol */
.highlight .bp { color: #008000 } /* Name.Builtin.Pseudo */
.highlight .fm { color: #0000FF } /* Name.Function.Magic */
.highlight .vc { color: #19177C } /* Name.Variable.Class */
.highlight .vg { color: #19177C } /* Name.Variable.Global */
.highlight .vi { color: #19177C } /* Name.Variable.Instance */
.highlight .vm { color: #19177C } /* Name.Variable.Magic */
.highlight .il { color: #666666 } /* Literal.Number.Integer.Long */
    </style>
<style type="text/css">
    
/* Temporary definitions which will become obsolete with Notebook release 5.0 */
.ansi-black-fg { color: #3E424D; }
.ansi-black-bg { background-color: #3E424D; }
.ansi-black-intense-fg { color: #282C36; }
.ansi-black-intense-bg { background-color: #282C36; }
.ansi-red-fg { color: #E75C58; }
.ansi-red-bg { background-color: #E75C58; }
.ansi-red-intense-fg { color: #B22B31; }
.ansi-red-intense-bg { background-color: #B22B31; }
.ansi-green-fg { color: #00A250; }
.ansi-green-bg { background-color: #00A250; }
.ansi-green-intense-fg { color: #007427; }
.ansi-green-intense-bg { background-color: #007427; }
.ansi-yellow-fg { color: #DDB62B; }
.ansi-yellow-bg { background-color: #DDB62B; }
.ansi-yellow-intense-fg { color: #B27D12; }
.ansi-yellow-intense-bg { background-color: #B27D12; }
.ansi-blue-fg { color: #208FFB; }
.ansi-blue-bg { background-color: #208FFB; }
.ansi-blue-intense-fg { color: #0065CA; }
.ansi-blue-intense-bg { background-color: #0065CA; }
.ansi-magenta-fg { color: #D160C4; }
.ansi-magenta-bg { background-color: #D160C4; }
.ansi-magenta-intense-fg { color: #A03196; }
.ansi-magenta-intense-bg { background-color: #A03196; }
.ansi-cyan-fg { color: #60C6C8; }
.ansi-cyan-bg { background-color: #60C6C8; }
.ansi-cyan-intense-fg { color: #258F8F; }
.ansi-cyan-intense-bg { background-color: #258F8F; }
.ansi-white-fg { color: #C5C1B4; }
.ansi-white-bg { background-color: #C5C1B4; }
.ansi-white-intense-fg { color: #A1A6B2; }
.ansi-white-intense-bg { background-color: #A1A6B2; }

.ansi-bold { font-weight: bold; }

    </style>


<style type="text/css">
/* Overrides of notebook CSS for static HTML export */
body {
  overflow: visible;
  padding: 8px;
}

div#notebook {
  overflow: visible;
  border-top: none;
}@media print {
  div.cell {
    display: block;
    page-break-inside: avoid;
  } 
  div.output_wrapper { 
    display: block;
    page-break-inside: avoid; 
  }
  div.output { 
    display: block;
    page-break-inside: avoid; 
  }
}
</style>

<!-- Custom stylesheet, it must be in the same directory as the html file -->
<link rel="stylesheet" href="custom.css">

<!-- Loading mathjax macro -->
<!-- Load mathjax -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-AMS_HTML"></script>
    <!-- MathJax configuration -->
    <script type="text/x-mathjax-config">
    MathJax.Hub.Config({
        tex2jax: {
            inlineMath: [ ['$','$'], ["\\(","\\)"] ],
            displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
            processEscapes: true,
            processEnvironments: true
        },
        // Center justify equations in code and markdown cells. Elsewhere
        // we use CSS to left justify single line equations in code cells.
        displayAlign: 'center',
        "HTML-CSS": {
            styles: {'.MathJax_Display': {"margin": 0}},
            linebreaks: { automatic: true }
        }
    });
    </script>
    <!-- End of mathjax configuration --></head>
<body>
  <div tabindex="-1" id="notebook" class="border-box-sizing">
    <div class="container" id="notebook-container">

<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><b></p>
<p>
<center>
<font size="6">
Project 3: Airbnb Pricing Strategy
</font>
</center>
</p><p>
<center>
<font size="4">
By Gaofeng Huang
</font>
</center>
</p><p>
<center>
<font size="3">
Class: DATS6103 Data Mining (19Spring) of 15:30-18:00, Thursday.
</font>
</center>
</p><p>
<center>
<font size="3">
<a href="https://public.opendatasoft.com/explore/dataset/airbnb-listings/export/?disjunctive.host_verifications&disjunctive.amenities&disjunctive.features&location=15,51.5198,-0.16183&basemap=jawg.streets&dataChart=eyJxdWVyaWVzIjpbeyJjaGFydHMiOlt7InR5cGUiOiJjb2x1bW4iLCJmdW5jIjoiQ09VTlQiLCJ5QXhpcyI6Imhvc3RfbGlzdGluZ3NfY291bnQiLCJzY2llbnRpZmljRGlzcGxheSI6dHJ1ZSwiY29sb3IiOiJyYW5nZS1jdXN0b20ifV0sInhBeGlzIjoiY2l0eSIsIm1heHBvaW50cyI6IiIsInRpbWVzY2FsZSI6IiIsInNvcnQiOiIiLCJzZXJpZXNCcmVha2Rvd24iOiJyb29tX3R5cGUiLCJjb25maWciOnsiZGF0YXNldCI6ImFpcmJuYi1saXN0aW5ncyIsIm9wdGlvbnMiOnsiZGlzanVuY3RpdmUuaG9zdF92ZXJpZmljYXRpb25zIjp0cnVlLCJkaXNqdW5jdGl2ZS5hbWVuaXRpZXMiOnRydWUsImRpc2p1bmN0aXZlLmZlYXR1cmVzIjp0cnVlfX19XSwidGltZXNjYWxlIjoiIiwiZGlzcGxheUxlZ2VuZCI6dHJ1ZSwiYWxpZ25Nb250aCI6dHJ1ZX0%3D">
    Source 1: Airbnb Listings 
    </a><br>
<a href="https://data.worldbank.org/indicator/ST.INT.ARVL">
    Source 2: World Bank Tourists Arrivals 
    </a><br>
<a href="https://github.com/lucasmonteiro001/free-world-hotel-database/blob/master/hotels.csv.zip">
    Source 3: Hotels Data From GitHub 
    </a><br>
</font>
</center>
</p><p>&lt;/b&gt;</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Publication">Publication<a class="anchor-link" href="#Publication">&#182;</a></h2><p>Github: [<a href="https://github.com/GH920/DATS-6103-Individual-Project-3">https://github.com/GH920/DATS-6103-Individual-Project-3</a>]</p>
<p>Zenodo: [<a href="https://sandbox.zenodo.org/record/280575#.XM4-CJNKiqA">https://sandbox.zenodo.org/record/280575#.XM4-CJNKiqA</a>]</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[1]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">pp</span>
<span class="kn">import</span> <span class="nn">seaborn</span> <span class="k">as</span> <span class="nn">sns</span>
<span class="kn">import</span> <span class="nn">csv</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[2]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">plotly</span>
<span class="kn">import</span> <span class="nn">plotly.plotly</span> <span class="k">as</span> <span class="nn">py</span>
<span class="kn">from</span> <span class="nn">plotly.graph_objs</span> <span class="k">import</span> <span class="o">*</span>
<span class="n">py</span><span class="o">.</span><span class="n">sign_in</span><span class="p">(</span><span class="s1">&#39;ghuang920&#39;</span><span class="p">,</span><span class="s1">&#39;8iaLjzlhEXT9N0gAYZ1O&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[3]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#colorscale made for plotting</span>
<span class="n">scale1</span> <span class="o">=</span> <span class="p">[[</span><span class="mf">0.0</span><span class="p">,</span> <span class="s1">&#39;rgb(0,100,0)&#39;</span><span class="p">],[</span><span class="mf">0.2</span><span class="p">,</span> <span class="s1">&#39;rgb(34,139,34)&#39;</span><span class="p">],</span>
         <span class="p">[</span><span class="mf">0.4</span><span class="p">,</span> <span class="s1">&#39;rgb(60,179,60)&#39;</span><span class="p">],[</span><span class="mf">0.6</span><span class="p">,</span> <span class="s1">&#39;rgb(173,255,47)&#39;</span><span class="p">],</span>
         <span class="p">[</span><span class="mf">0.8</span><span class="p">,</span> <span class="s1">&#39;rgb(255,215,0)&#39;</span><span class="p">],[</span><span class="mf">1.0</span><span class="p">,</span> <span class="s1">&#39;rgb(255,99,71)&#39;</span><span class="p">]]</span>
<span class="n">scale2</span> <span class="o">=</span> <span class="p">[</span>
          <span class="p">[</span><span class="mf">0.0</span><span class="p">,</span> <span class="s2">&quot;rgb(242,240,247)&quot;</span><span class="p">],</span> 
          <span class="p">[</span><span class="mf">0.2</span><span class="p">,</span> <span class="s2">&quot;rgb(218,218,235)&quot;</span><span class="p">],</span> 
          <span class="p">[</span><span class="mf">0.4</span><span class="p">,</span> <span class="s2">&quot;rgb(188,189,220)&quot;</span><span class="p">],</span>
          <span class="p">[</span><span class="mf">0.6</span><span class="p">,</span> <span class="s2">&quot;rgb(158,154,200)&quot;</span><span class="p">],</span> 
          <span class="p">[</span><span class="mf">0.8</span><span class="p">,</span> <span class="s2">&quot;rgb(117,107,177)&quot;</span><span class="p">],</span> 
          <span class="p">[</span><span class="mf">1.0</span><span class="p">,</span> <span class="s2">&quot;rgb(84,39,143)&quot;</span><span class="p">]</span>
      <span class="p">]</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[4]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">sns</span><span class="o">.</span><span class="n">set</span><span class="p">(</span><span class="n">rc</span><span class="o">=</span><span class="p">{</span><span class="s1">&#39;figure.figsize&#39;</span><span class="p">:(</span><span class="mi">12</span><span class="p">,</span><span class="mi">8</span><span class="p">)})</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[5]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Due to some reason about the data itself, we only choose these 13 countries to analyze</span>
<span class="n">countries</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;Australia&#39;</span><span class="p">,</span> <span class="s1">&#39;Austria&#39;</span><span class="p">,</span> <span class="s1">&#39;Belgium&#39;</span><span class="p">,</span> <span class="s1">&#39;Canada&#39;</span><span class="p">,</span> 
             <span class="s1">&#39;France&#39;</span><span class="p">,</span> <span class="s1">&#39;Germany&#39;</span><span class="p">,</span> <span class="s1">&#39;Greece&#39;</span><span class="p">,</span> <span class="s1">&#39;Ireland&#39;</span><span class="p">,</span> <span class="s1">&#39;Italy&#39;</span><span class="p">,</span> 
             <span class="s1">&#39;Netherlands&#39;</span><span class="p">,</span> <span class="s1">&#39;Spain&#39;</span><span class="p">,</span> <span class="s1">&#39;United Kingdom&#39;</span><span class="p">,</span> <span class="s1">&#39;United States&#39;</span><span class="p">]</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Dataset-of-tourists-inflow">Dataset of tourists inflow<a class="anchor-link" href="#Dataset-of-tourists-inflow">&#182;</a></h2>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[6]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># World Bank data, travel inflow by country</span>
<span class="n">travel_raw</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s1">&#39;TravelNumber.csv&#39;</span><span class="p">,</span> <span class="n">skiprows</span><span class="o">=</span><span class="mi">3</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[7]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Get the information about the countries</span>
<span class="n">meta</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s1">&#39;Meta_Country.csv&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[8]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">meta</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[8]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country Code</th>
      <th>Region</th>
      <th>IncomeGroup</th>
      <th>SpecialNotes</th>
      <th>TableName</th>
      <th>Unnamed: 5</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>ABW</td>
      <td>Latin America &amp; Caribbean</td>
      <td>High income</td>
      <td>Central Bureau of Statistics and Central Bank ...</td>
      <td>Aruba</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>AFG</td>
      <td>South Asia</td>
      <td>Low income</td>
      <td>Central Statistics Organization; World Bank st...</td>
      <td>Afghanistan</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>AGO</td>
      <td>Sub-Saharan Africa</td>
      <td>Lower middle income</td>
      <td>IMF ; Source of population estimates: UN Popul...</td>
      <td>Angola</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>ALB</td>
      <td>Europe &amp; Central Asia</td>
      <td>Upper middle income</td>
      <td>Albanian Institute of Statistics ; Source of p...</td>
      <td>Albania</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>AND</td>
      <td>Europe &amp; Central Asia</td>
      <td>High income</td>
      <td>Government of Andorra, Department of Statistic...</td>
      <td>Andorra</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[9]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">metaOut</span> <span class="o">=</span> <span class="n">meta</span><span class="o">.</span><span class="n">loc</span><span class="p">[:,[</span><span class="s1">&#39;Country Code&#39;</span><span class="p">,</span> <span class="s1">&#39;Region&#39;</span><span class="p">,</span> <span class="s1">&#39;IncomeGroup&#39;</span><span class="p">]]</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[10]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">travel_toclean</span> <span class="o">=</span> <span class="n">travel_raw</span><span class="o">.</span><span class="n">merge</span><span class="p">(</span><span class="n">metaOut</span><span class="p">,</span> <span class="n">on</span><span class="o">=</span><span class="s1">&#39;Country Code&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[11]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">years</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;2012&#39;</span><span class="p">,</span><span class="s1">&#39;2013&#39;</span><span class="p">,</span><span class="s1">&#39;2014&#39;</span><span class="p">,</span><span class="s1">&#39;2015&#39;</span><span class="p">,</span><span class="s1">&#39;2016&#39;</span><span class="p">,</span><span class="s1">&#39;2017&#39;</span><span class="p">]</span>
<span class="n">travel</span> <span class="o">=</span> <span class="n">travel_toclean</span><span class="o">.</span><span class="n">loc</span><span class="p">[:,</span> <span class="p">[</span><span class="s1">&#39;Country Name&#39;</span><span class="p">,</span> <span class="s1">&#39;Country Code&#39;</span><span class="p">,</span> <span class="s1">&#39;Region&#39;</span><span class="p">,</span> <span class="s1">&#39;IncomeGroup&#39;</span><span class="p">]</span> <span class="o">+</span> <span class="n">years</span><span class="p">]</span>
<span class="n">travel</span><span class="o">.</span><span class="n">head</span><span class="p">(</span><span class="mi">10</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[11]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country Name</th>
      <th>Country Code</th>
      <th>Region</th>
      <th>IncomeGroup</th>
      <th>2012</th>
      <th>2013</th>
      <th>2014</th>
      <th>2015</th>
      <th>2016</th>
      <th>2017</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Aruba</td>
      <td>ABW</td>
      <td>Latin America &amp; Caribbean</td>
      <td>High income</td>
      <td>9.040000e+05</td>
      <td>9.790000e+05</td>
      <td>1.072000e+06</td>
      <td>1.225000e+06</td>
      <td>1.102000e+06</td>
      <td>1.070500e+06</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>South Asia</td>
      <td>Low income</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Angola</td>
      <td>AGO</td>
      <td>Sub-Saharan Africa</td>
      <td>Lower middle income</td>
      <td>5.280000e+05</td>
      <td>6.500000e+05</td>
      <td>5.950000e+05</td>
      <td>5.920000e+05</td>
      <td>3.970000e+05</td>
      <td>2.610000e+05</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Albania</td>
      <td>ALB</td>
      <td>Europe &amp; Central Asia</td>
      <td>Upper middle income</td>
      <td>3.156000e+06</td>
      <td>2.857000e+06</td>
      <td>3.341000e+06</td>
      <td>3.784000e+06</td>
      <td>4.070000e+06</td>
      <td>4.643000e+06</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Andorra</td>
      <td>AND</td>
      <td>Europe &amp; Central Asia</td>
      <td>High income</td>
      <td>2.238000e+06</td>
      <td>2.328000e+06</td>
      <td>2.363000e+06</td>
      <td>2.663000e+06</td>
      <td>2.831000e+06</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Arab World</td>
      <td>ARB</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>7.899196e+07</td>
      <td>7.869716e+07</td>
      <td>8.415708e+07</td>
      <td>7.885381e+07</td>
      <td>7.636341e+07</td>
      <td>8.221460e+07</td>
    </tr>
    <tr>
      <th>6</th>
      <td>United Arab Emirates</td>
      <td>ARE</td>
      <td>Middle East &amp; North Africa</td>
      <td>High income</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Argentina</td>
      <td>ARG</td>
      <td>Latin America &amp; Caribbean</td>
      <td>High income</td>
      <td>5.587000e+06</td>
      <td>5.246000e+06</td>
      <td>5.931000e+06</td>
      <td>5.736000e+06</td>
      <td>6.655000e+06</td>
      <td>6.720000e+06</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Armenia</td>
      <td>ARM</td>
      <td>Europe &amp; Central Asia</td>
      <td>Upper middle income</td>
      <td>9.630000e+05</td>
      <td>1.084000e+06</td>
      <td>1.204000e+06</td>
      <td>1.192000e+06</td>
      <td>1.260000e+06</td>
      <td>1.495000e+06</td>
    </tr>
    <tr>
      <th>9</th>
      <td>American Samoa</td>
      <td>ASM</td>
      <td>East Asia &amp; Pacific</td>
      <td>Upper middle income</td>
      <td>2.260000e+04</td>
      <td>2.080000e+04</td>
      <td>2.160000e+04</td>
      <td>2.030000e+04</td>
      <td>2.010000e+04</td>
      <td>2.000000e+04</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[12]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">travelinmap</span><span class="p">(</span><span class="n">dataset</span><span class="p">,</span> <span class="n">year</span><span class="p">):</span>

    <span class="n">trace1</span> <span class="o">=</span> <span class="nb">dict</span><span class="p">(</span>
                  <span class="n">z</span><span class="o">=</span><span class="n">dataset</span><span class="p">[</span><span class="n">year</span><span class="p">],</span>
                  <span class="n">autocolorscale</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span> 
                  <span class="n">colorbar</span><span class="o">=</span><span class="p">{</span><span class="s2">&quot;title&quot;</span><span class="p">:</span> <span class="s2">&quot;Tourists Inflow&quot;</span><span class="p">},</span> 
                  <span class="n">colorscale</span><span class="o">=</span><span class="n">scale2</span><span class="p">,</span> 
                  <span class="n">locations</span><span class="o">=</span><span class="n">dataset</span><span class="p">[</span><span class="s1">&#39;Country Code&#39;</span><span class="p">],</span>
                  <span class="n">marker</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">line</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">color</span><span class="o">=</span><span class="s2">&quot;rgb(180,180,180)&quot;</span><span class="p">,</span> 
                                        <span class="n">width</span><span class="o">=</span><span class="mf">0.5</span><span class="p">)),</span> 
                  <span class="n">reversescale</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span> 
                  <span class="n">text</span><span class="o">=</span><span class="n">dataset</span><span class="p">[</span><span class="s1">&#39;Country Name&#39;</span><span class="p">],</span>
                  <span class="nb">type</span><span class="o">=</span><span class="s2">&quot;choropleth&quot;</span><span class="p">,</span> 
                  <span class="n">zmax</span><span class="o">=</span><span class="mi">10</span><span class="o">**</span><span class="mi">8</span><span class="p">,</span>
                  <span class="n">zmin</span><span class="o">=</span><span class="mi">10</span><span class="o">**</span><span class="mi">4</span>
    <span class="p">)</span>
    <span class="n">data</span> <span class="o">=</span> <span class="p">[</span><span class="n">trace1</span><span class="p">]</span>

    <span class="n">layout</span> <span class="o">=</span> <span class="nb">dict</span><span class="p">(</span>
                  <span class="n">geo</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">projection</span><span class="o">=</span><span class="p">{</span><span class="s2">&quot;type&quot;</span><span class="p">:</span> <span class="s2">&quot;Mercator&quot;</span><span class="p">},</span> 
                           <span class="n">showcoastlines</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> 
                           <span class="n">showframe</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span>
                           <span class="c1">#showland=True,</span>
                           <span class="c1">#landcolor=&#39;rgb(220,220,220)&#39;</span>
                  <span class="p">),</span> 
                  <span class="n">title</span><span class="o">=</span><span class="s2">&quot;World Map of Tourists Inflow&quot;</span>
    <span class="p">)</span>
    <span class="n">fig</span> <span class="o">=</span> <span class="nb">dict</span><span class="p">(</span><span class="n">data</span><span class="o">=</span><span class="n">data</span><span class="p">,</span> <span class="n">layout</span><span class="o">=</span><span class="n">layout</span><span class="p">)</span>
    <span class="k">return</span> <span class="n">py</span><span class="o">.</span><span class="n">iplot</span><span class="p">(</span><span class="n">fig</span><span class="p">,</span> <span class="n">validate</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span> <span class="n">filename</span><span class="o">=</span><span class="s1">&#39;travel&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[13]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">travelinmap</span><span class="p">(</span><span class="n">travel</span><span class="p">,</span> <span class="s1">&#39;2015&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stderr output_text">
<pre>/Users/Hope/anaconda3/lib/python3.7/site-packages/IPython/core/display.py:689: UserWarning:

Consider using IPython.display.IFrame instead

</pre>
</div>
</div>

<div class="output_area">

    <div class="prompt output_prompt">Out[13]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<iframe id="igraph" scrolling="no" style="border:none;" seamless="seamless" src="https://plot.ly/~ghuang920/49.embed" height="525px" width="100%"></iframe>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Dataset-of-Airbnb-listings">Dataset of Airbnb listings<a class="anchor-link" href="#Dataset-of-Airbnb-listings">&#182;</a></h2><p>To note that this dataset is not the raw dataset. The raw dataset (about 2GB) can be downloaded in the link showed in the beginning part. This dataset of Airbnb is only 100MB+.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[14]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">airbnb_rawdata</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s1">&#39;airbnb.csv&#39;</span><span class="p">,</span> <span class="n">sep</span><span class="o">=</span><span class="s1">&#39;;&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stderr output_text">
<pre>/Users/Hope/anaconda3/lib/python3.7/site-packages/IPython/core/interactiveshell.py:3020: DtypeWarning:

Columns (1) have mixed types. Specify dtype option on import or set low_memory=False.

</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[15]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">airbnb_rawdata</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[15]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Unnamed: 0</th>
      <th>ID</th>
      <th>Last Scraped</th>
      <th>Name</th>
      <th>Host ID</th>
      <th>Host Response Time</th>
      <th>Host Response Rate</th>
      <th>Host Acceptance Rate</th>
      <th>Host Listings Count</th>
      <th>Host Total Listings Count</th>
      <th>...</th>
      <th>Review Scores Rating</th>
      <th>Review Scores Accuracy</th>
      <th>Review Scores Cleanliness</th>
      <th>Review Scores Checkin</th>
      <th>Review Scores Communication</th>
      <th>Review Scores Location</th>
      <th>Review Scores Value</th>
      <th>Cancellation Policy</th>
      <th>Calculated host listings count</th>
      <th>Reviews per Month</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>2501888</td>
      <td>2017-03-07</td>
      <td>Private bed in home</td>
      <td>12806524</td>
      <td>within an hour</td>
      <td>100.0</td>
      <td>NaN</td>
      <td>2.0</td>
      <td>2.0</td>
      <td>...</td>
      <td>94.0</td>
      <td>10.0</td>
      <td>9.0</td>
      <td>10.0</td>
      <td>10.0</td>
      <td>9.0</td>
      <td>9.0</td>
      <td>flexible</td>
      <td>1.0</td>
      <td>2.42</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>377609</td>
      <td>2017-03-07</td>
      <td>Lake House minutes to Downtown</td>
      <td>1897470</td>
      <td>within a few hours</td>
      <td>100.0</td>
      <td>NaN</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>...</td>
      <td>96.0</td>
      <td>9.0</td>
      <td>9.0</td>
      <td>10.0</td>
      <td>10.0</td>
      <td>10.0</td>
      <td>9.0</td>
      <td>strict</td>
      <td>1.0</td>
      <td>0.54</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>15643010</td>
      <td>2017-03-07</td>
      <td>Modern New Apartment Close to Everything!</td>
      <td>59461475</td>
      <td>within an hour</td>
      <td>100.0</td>
      <td>NaN</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>...</td>
      <td>97.0</td>
      <td>10.0</td>
      <td>10.0</td>
      <td>10.0</td>
      <td>10.0</td>
      <td>10.0</td>
      <td>10.0</td>
      <td>moderate</td>
      <td>1.0</td>
      <td>1.86</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>2236988</td>
      <td>2017-03-07</td>
      <td>Austin Waterfront Retreat</td>
      <td>11421571</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>...</td>
      <td>96.0</td>
      <td>9.0</td>
      <td>10.0</td>
      <td>10.0</td>
      <td>10.0</td>
      <td>10.0</td>
      <td>10.0</td>
      <td>strict</td>
      <td>1.0</td>
      <td>0.21</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>14788276</td>
      <td>2017-03-07</td>
      <td>Stay at the Domain's hotest residencial property.</td>
      <td>45591877</td>
      <td>a few days or more</td>
      <td>0.0</td>
      <td>NaN</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>...</td>
      <td>93.0</td>
      <td>9.0</td>
      <td>9.0</td>
      <td>10.0</td>
      <td>10.0</td>
      <td>10.0</td>
      <td>9.0</td>
      <td>moderate</td>
      <td>1.0</td>
      <td>0.69</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 53 columns</p>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[16]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># drop the &quot;Unnamed: 0&quot; column</span>
<span class="n">airbnb_raw</span> <span class="o">=</span> <span class="n">airbnb_rawdata</span><span class="o">.</span><span class="n">drop</span><span class="p">([</span><span class="s2">&quot;Unnamed: 0&quot;</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[17]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">airbnb_raw</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[17]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>Last Scraped</th>
      <th>Name</th>
      <th>Host ID</th>
      <th>Host Response Time</th>
      <th>Host Response Rate</th>
      <th>Host Acceptance Rate</th>
      <th>Host Listings Count</th>
      <th>Host Total Listings Count</th>
      <th>City</th>
      <th>...</th>
      <th>Review Scores Rating</th>
      <th>Review Scores Accuracy</th>
      <th>Review Scores Cleanliness</th>
      <th>Review Scores Checkin</th>
      <th>Review Scores Communication</th>
      <th>Review Scores Location</th>
      <th>Review Scores Value</th>
      <th>Cancellation Policy</th>
      <th>Calculated host listings count</th>
      <th>Reviews per Month</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2501888</td>
      <td>2017-03-07</td>
      <td>Private bed in home</td>
      <td>12806524</td>
      <td>within an hour</td>
      <td>100.0</td>
      <td>NaN</td>
      <td>2.0</td>
      <td>2.0</td>
      <td>West Lake Hills</td>
      <td>...</td>
      <td>94.0</td>
      <td>10.0</td>
      <td>9.0</td>
      <td>10.0</td>
      <td>10.0</td>
      <td>9.0</td>
      <td>9.0</td>
      <td>flexible</td>
      <td>1.0</td>
      <td>2.42</td>
    </tr>
    <tr>
      <th>1</th>
      <td>377609</td>
      <td>2017-03-07</td>
      <td>Lake House minutes to Downtown</td>
      <td>1897470</td>
      <td>within a few hours</td>
      <td>100.0</td>
      <td>NaN</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>Austin</td>
      <td>...</td>
      <td>96.0</td>
      <td>9.0</td>
      <td>9.0</td>
      <td>10.0</td>
      <td>10.0</td>
      <td>10.0</td>
      <td>9.0</td>
      <td>strict</td>
      <td>1.0</td>
      <td>0.54</td>
    </tr>
    <tr>
      <th>2</th>
      <td>15643010</td>
      <td>2017-03-07</td>
      <td>Modern New Apartment Close to Everything!</td>
      <td>59461475</td>
      <td>within an hour</td>
      <td>100.0</td>
      <td>NaN</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>Austin</td>
      <td>...</td>
      <td>97.0</td>
      <td>10.0</td>
      <td>10.0</td>
      <td>10.0</td>
      <td>10.0</td>
      <td>10.0</td>
      <td>10.0</td>
      <td>moderate</td>
      <td>1.0</td>
      <td>1.86</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2236988</td>
      <td>2017-03-07</td>
      <td>Austin Waterfront Retreat</td>
      <td>11421571</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>Austin</td>
      <td>...</td>
      <td>96.0</td>
      <td>9.0</td>
      <td>10.0</td>
      <td>10.0</td>
      <td>10.0</td>
      <td>10.0</td>
      <td>10.0</td>
      <td>strict</td>
      <td>1.0</td>
      <td>0.21</td>
    </tr>
    <tr>
      <th>4</th>
      <td>14788276</td>
      <td>2017-03-07</td>
      <td>Stay at the Domain's hotest residencial property.</td>
      <td>45591877</td>
      <td>a few days or more</td>
      <td>0.0</td>
      <td>NaN</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>Austin</td>
      <td>...</td>
      <td>93.0</td>
      <td>9.0</td>
      <td>9.0</td>
      <td>10.0</td>
      <td>10.0</td>
      <td>10.0</td>
      <td>9.0</td>
      <td>moderate</td>
      <td>1.0</td>
      <td>0.69</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 52 columns</p>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[18]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">airbnb_raw</span><span class="o">.</span><span class="n">shape</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[18]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>(494954, 52)</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[19]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">airbnb_raw</span><span class="o">.</span><span class="n">columns</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[19]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>Index([&#39;ID&#39;, &#39;Last Scraped&#39;, &#39;Name&#39;, &#39;Host ID&#39;, &#39;Host Response Time&#39;,
       &#39;Host Response Rate&#39;, &#39;Host Acceptance Rate&#39;, &#39;Host Listings Count&#39;,
       &#39;Host Total Listings Count&#39;, &#39;City&#39;, &#39;State&#39;, &#39;Zipcode&#39;, &#39;Market&#39;,
       &#39;Country Code&#39;, &#39;Country&#39;, &#39;Latitude&#39;, &#39;Longitude&#39;, &#39;Property Type&#39;,
       &#39;Room Type&#39;, &#39;Accommodates&#39;, &#39;Bathrooms&#39;, &#39;Bedrooms&#39;, &#39;Beds&#39;,
       &#39;Bed Type&#39;, &#39;Square Feet&#39;, &#39;Price&#39;, &#39;Weekly Price&#39;, &#39;Monthly Price&#39;,
       &#39;Security Deposit&#39;, &#39;Cleaning Fee&#39;, &#39;Guests Included&#39;, &#39;Extra People&#39;,
       &#39;Minimum Nights&#39;, &#39;Maximum Nights&#39;, &#39;Calendar Updated&#39;,
       &#39;Availability 30&#39;, &#39;Availability 60&#39;, &#39;Availability 90&#39;,
       &#39;Availability 365&#39;, &#39;Number of Reviews&#39;, &#39;First Review&#39;, &#39;Last Review&#39;,
       &#39;Review Scores Rating&#39;, &#39;Review Scores Accuracy&#39;,
       &#39;Review Scores Cleanliness&#39;, &#39;Review Scores Checkin&#39;,
       &#39;Review Scores Communication&#39;, &#39;Review Scores Location&#39;,
       &#39;Review Scores Value&#39;, &#39;Cancellation Policy&#39;,
       &#39;Calculated host listings count&#39;, &#39;Reviews per Month&#39;],
      dtype=&#39;object&#39;)</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>In order to merge these dataset together, country code is the most suitable variable to be used in the combination of data. However, the code in World Bank data has 3 letters while it has 2 letters in other two datasets. Therefore, we should convert the 2-letter code into 3-letter for consistency.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[20]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># 2-letter country codes cannot be recognized by plotly</span>
<span class="c1"># so we turn it into 3-letter codes</span>
<span class="k">def</span> <span class="nf">countrycode2to3</span><span class="p">(</span><span class="n">rawdata</span><span class="p">,</span> <span class="n">on</span><span class="o">=</span><span class="s1">&#39;Country&#39;</span><span class="p">,</span> <span class="n">code</span><span class="o">=</span><span class="s1">&#39;Country Code&#39;</span><span class="p">):</span>
    <span class="n">data</span> <span class="o">=</span> <span class="n">rawdata</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="n">code</span><span class="p">,</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
    <span class="c1">#get 3 code from World Bank data</span>
    <span class="n">meta_code</span> <span class="o">=</span> <span class="n">travel</span><span class="o">.</span><span class="n">loc</span><span class="p">[:,[</span><span class="s1">&#39;Country Name&#39;</span><span class="p">,</span><span class="s1">&#39;Country Code&#39;</span><span class="p">]]</span>
    <span class="n">meta_code_tomerge</span> <span class="o">=</span> <span class="n">meta_code</span><span class="o">.</span><span class="n">rename</span><span class="p">(</span><span class="n">columns</span><span class="o">=</span><span class="p">{</span><span class="s1">&#39;Country Name&#39;</span><span class="p">:</span> <span class="n">on</span><span class="p">,</span> <span class="s1">&#39;Country Code&#39;</span><span class="p">:</span> <span class="n">code</span><span class="p">})</span>
    
    <span class="n">dataout</span> <span class="o">=</span> <span class="n">data</span><span class="o">.</span><span class="n">merge</span><span class="p">(</span><span class="n">meta_code_tomerge</span><span class="p">,</span> <span class="n">on</span><span class="o">=</span><span class="n">on</span><span class="p">)</span>
    <span class="k">return</span> <span class="n">dataout</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[21]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">airbnb</span> <span class="o">=</span> <span class="n">countrycode2to3</span><span class="p">(</span><span class="n">airbnb_raw</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[22]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">airbnb_priceonly</span> <span class="o">=</span> <span class="n">airbnb</span><span class="o">.</span><span class="n">loc</span><span class="p">[:,[</span><span class="s1">&#39;Price&#39;</span><span class="p">,</span> <span class="s1">&#39;Country&#39;</span><span class="p">,</span> <span class="s1">&#39;Country Code&#39;</span><span class="p">]]</span>
<span class="n">airbnb_byprice</span> <span class="o">=</span> <span class="n">airbnb_priceonly</span><span class="o">.</span><span class="n">groupby</span><span class="p">([</span><span class="s1">&#39;Country&#39;</span><span class="p">,</span> <span class="s1">&#39;Country Code&#39;</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="mi">0</span><span class="p">)</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span>
<span class="n">airbnb_byprice</span><span class="p">[</span><span class="s1">&#39;Count&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">airbnb_priceonly</span><span class="o">.</span><span class="n">groupby</span><span class="p">([</span><span class="s1">&#39;Country&#39;</span><span class="p">,</span> <span class="s1">&#39;Country Code&#39;</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="mi">0</span><span class="p">)</span><span class="o">.</span><span class="n">count</span><span class="p">()[</span><span class="s1">&#39;Price&#39;</span><span class="p">]</span>
<span class="n">airbnb_byprice</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[22]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th></th>
      <th>Price</th>
      <th>Count</th>
    </tr>
    <tr>
      <th>Country</th>
      <th>Country Code</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Australia</th>
      <th>AUS</th>
      <td>165.077177</td>
      <td>40219</td>
    </tr>
    <tr>
      <th>Austria</th>
      <th>AUT</th>
      <td>67.076562</td>
      <td>7889</td>
    </tr>
    <tr>
      <th>Belgium</th>
      <th>BEL</th>
      <td>68.052057</td>
      <td>7415</td>
    </tr>
    <tr>
      <th>Canada</th>
      <th>CAN</th>
      <td>107.010622</td>
      <td>30692</td>
    </tr>
    <tr>
      <th>China</th>
      <th>CHN</th>
      <td>320.300000</td>
      <td>50</td>
    </tr>
    <tr>
      <th>Cuba</th>
      <th>CUB</th>
      <td>102.000000</td>
      <td>1</td>
    </tr>
    <tr>
      <th>Denmark</th>
      <th>DNK</th>
      <td>596.433339</td>
      <td>16569</td>
    </tr>
    <tr>
      <th>France</th>
      <th>FRA</th>
      <td>94.431201</td>
      <td>56505</td>
    </tr>
    <tr>
      <th>Germany</th>
      <th>DEU</th>
      <td>57.222044</td>
      <td>20568</td>
    </tr>
    <tr>
      <th>Greece</th>
      <th>GRC</th>
      <td>52.935767</td>
      <td>5122</td>
    </tr>
    <tr>
      <th>Ireland</th>
      <th>IRL</th>
      <td>103.780488</td>
      <td>6724</td>
    </tr>
    <tr>
      <th>Italy</th>
      <th>ITA</th>
      <td>93.964180</td>
      <td>33110</td>
    </tr>
    <tr>
      <th>Mexico</th>
      <th>MEX</th>
      <td>25.000000</td>
      <td>2</td>
    </tr>
    <tr>
      <th>Netherlands</th>
      <th>NLD</th>
      <td>133.993607</td>
      <td>15173</td>
    </tr>
    <tr>
      <th>Spain</th>
      <th>ESP</th>
      <td>97.136425</td>
      <td>45732</td>
    </tr>
    <tr>
      <th>Switzerland</th>
      <th>CHE</th>
      <td>120.157806</td>
      <td>2370</td>
    </tr>
    <tr>
      <th>United Kingdom</th>
      <th>GBR</th>
      <td>93.020880</td>
      <td>60966</td>
    </tr>
    <tr>
      <th>United States</th>
      <th>USA</th>
      <td>156.051199</td>
      <td>132581</td>
    </tr>
    <tr>
      <th>Uruguay</th>
      <th>URY</th>
      <td>237.000000</td>
      <td>1</td>
    </tr>
    <tr>
      <th>Vanuatu</th>
      <th>VUT</th>
      <td>110.000000</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[23]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">airbnb_byprice</span><span class="o">.</span><span class="n">reset_index</span><span class="p">()</span><span class="o">.</span><span class="n">plot</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">x</span><span class="o">=</span><span class="s1">&#39;Country&#39;</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">&#39;Count&#39;</span><span class="p">)</span>
<span class="n">pp</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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hg0bZvTv+bFmzpypyspKrVy5Ui+88IIOHDig2NhYDRs2TO3atTvv6//kk08a/r+mpkabN2+W1+s1XsBlwbIsy7rzzjsty7KsV1991VqxYoVlWZYVFxdnPMeIESOsqqoqa9myZdarr75qWZZlDRo0yHiO6Ohoy+fzGV/vseLj4y3LsqyXXnrJWrt2rWVZlhUTE2M8R/3PxuLFi62VK1dalmVZgwcPNpph6NChlmVZ1nPPPWfl5uZaPp/P6GOxb9++hv82btxoDRgwwMrOzm4YM2nYsGGWZf3rMamrq7NiY2ONZjjWvn37rEWLFlk333yzNXLkSGvgwIHWqlWrjKzbLo9FfY5j1Wfyh1WrVlkRERFW7969rbFjx1q7d+82tu7BgwdbFRUVDbePHDliRUdHG1u/ZVlWQkKCZVmW9fvf/97KyclpyGWS6fWdyp133mkdOXKk4XZlZaV1xx13GM3wt7/9zZo7d66Vm5trbdiwoeE/k+Lj461//vOfVkREhPXdd99ZX331lTVkyBCjGY63ceNG68knn7Ruu+02KykpyRo8eLCVlpZmPMfBgwete++91/h62QP+f9q3b69Fixapf//+euaZZyQd/XjXtCFDhuihhx5Samqq7rzzTn344Ydq37698Ry9evXSnj171K1bN+PrrteqVSvt2rVLV111lTZs2KB+/fqppqbGeI7Q0FBlZGSoZ8+eeu211+TxeFRZWWk0g8vl0qFDh9S1a1d99tln6t+/v2pra42t/+67727Yi2VZloKDgzVnzhxJRz8Z+Z//+R9jWRwOh6qrqxvyHDx40C972N566y1lZmaqsLBQw4YN0+uvv64OHTooPz9f8fHxuu222857Brs8FiEhIVq2bJliYmJUV1enzMxMtW7d2miGPXv2aPny5VqxYoU6deqkCRMmaODAgfr444/1u9/9TqtWrTKSw7KsRuepuFwuOZ1m/9T+5Cc/0YwZM/TFF1/omWee0axZs9SpUyejGf7t3/5N27dvV48ePYyu93jH/07U1NTo0KFDRjN8+umn2rJli7Zs2dIwZvoT5aSkJM2ZM0f33XefunTpojvuuEOTJk0ytv5jzZs3TytWrNDll1+u4cOHa8qUKXK5XCorK9Mtt9yiu+++22ieSy65RPv27TO6TklyWNYxB2ddxMrKyrR27VrFxsYqLS1Nubm5uueee4wf31qfJTQ0VPv379c///lP3XTTTQoJCTGaISMjQ5MnT5bH41FgYKAsyzJetDZs2KAlS5bomWee0V133aXvvvtOw4cPN37CX35+vv7+97/rvvvu06xZs5Sbm6sHH3xQsbGxxjJkZ2crPT1dL7zwgkaMGKGAgAD16NFDzz77rLEM0tFjS2+++Waj6zxeRkaG3nrrLe3Zs0cxMTF677339Mc//tH4+Rp/+tOfNHz4cPXt2/eE+1auXKmoqKjznsEuj8W+ffs0Y8YMffLJJ3I4HBowYICmTp1qdOfBb37zGyUkJCg+Pv6EQwz+4z/+Q5MnTzaS4+mnn254EyZJ77zzjtq3b6+pU6caWb909G/I+++/r+uvv15XXnmllixZomHDhunSSy81liE+Pl7bt29Xu3bt5HK5/PI3RJL+/Oc/65133lFERIQsy9IHH3ygxMREjRo1yliGuLg4vfvuu8bWdyrl5eX6/vvvde2116qiokKXXHKJX3I899xzSkhIUJcuXU64z8TJ7aNHj260Q2nv3r2KiIjQ9OnTz+t6j3fRF/DCwkK53W7l5eWd9H5Tew3efPNN3Xnnnac8ccT08WMxMTF66qmnTth+08fOHevw4cPG96rZSf0fsCNHjmj37t3q0aOHAgLMXkk0NjZWf//7342u82T+93//V5988olqa2vVt29fv53c9M033+jw4cONTjIzeaKyZJ/HAkdZlqU33nhDH3/8sSzLUr9+/XTnnXca2Qt+qpPL6pk8xvVUexT98Tfkiy++0IYNG+RwONS/f3/je+Uff/xxjRkzxq+fBnz00UdKTk5WbW2t3nzzTcXFxSk1NVU33XST8SxVVVVat26dysvLJanhymLjxo0zsv4NGzY0/L/D4VCbNm109dVXG1n3sS76Q1CmTp2qRYsWNXzEfuwfUpPv1u32PqhNmzbyer1++Tj72HenJ2P6xJG3335bs2fPPuGKMNu2bTOWobS0VC+99JI2bNggp9Op/v37q2vXrsY/GenSpYsmTZqkXr16NfqY3eQf9h07dmjhwoWaN2+edu7cqeTkZM2YMcP44VJPPfWUVq9e3WgvjumPle3yWHz44YeaP3/+CW9GTLx+Hn8lluNfw03+nkpquFLR888/r/z8fP3tb39TTU2NkQJef3LZd999pz179igyMlKBgYFav369rr76aiO/p/Wfkp3qCjim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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>As mentioned in the beginning, we only care about 13 countries in this project because the data of other countries are insufficient or weird. For example, some countries (e.g. China, Cuba...) only have less than 50 oberservations. Also, some countries (e.g. Denmark...) have very strange data.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[24]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">airbnb_byprice_toplot</span> <span class="o">=</span> <span class="n">airbnb_byprice</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">countries</span><span class="p">,</span> <span class="p">:]</span><span class="o">.</span><span class="n">reset_index</span><span class="p">()</span>
<span class="n">airbnb_byprice_toplot</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[24]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>Country Code</th>
      <th>Price</th>
      <th>Count</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Australia</td>
      <td>AUS</td>
      <td>165.077177</td>
      <td>40219</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Austria</td>
      <td>AUT</td>
      <td>67.076562</td>
      <td>7889</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Belgium</td>
      <td>BEL</td>
      <td>68.052057</td>
      <td>7415</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Canada</td>
      <td>CAN</td>
      <td>107.010622</td>
      <td>30692</td>
    </tr>
    <tr>
      <th>4</th>
      <td>France</td>
      <td>FRA</td>
      <td>94.431201</td>
      <td>56505</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Germany</td>
      <td>DEU</td>
      <td>57.222044</td>
      <td>20568</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Greece</td>
      <td>GRC</td>
      <td>52.935767</td>
      <td>5122</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Ireland</td>
      <td>IRL</td>
      <td>103.780488</td>
      <td>6724</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Italy</td>
      <td>ITA</td>
      <td>93.964180</td>
      <td>33110</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Netherlands</td>
      <td>NLD</td>
      <td>133.993607</td>
      <td>15173</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Spain</td>
      <td>ESP</td>
      <td>97.136425</td>
      <td>45732</td>
    </tr>
    <tr>
      <th>11</th>
      <td>United Kingdom</td>
      <td>GBR</td>
      <td>93.020880</td>
      <td>60966</td>
    </tr>
    <tr>
      <th>12</th>
      <td>United States</td>
      <td>USA</td>
      <td>156.051199</td>
      <td>132581</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[25]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># the observation size w.r.t country</span>
<span class="n">airbnb_byprice_toplot</span><span class="o">.</span><span class="n">plot</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">x</span><span class="o">=</span><span class="s1">&#39;Country&#39;</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">&#39;Count&#39;</span><span class="p">)</span>
<span class="n">pp</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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9thj6tGjh9Vl+eXnP/+5du/erX79+lldSqt9+OGH+uCDD/TBBx80LwvUq8epqalauHCh7rjjDp1//vm66aabNGvWLKvLOiWH98TBS/i3qqqqtHnzZiUkJCg7O1tbt27VbbfdpiFDhlhdmt+O3wSzf/9+ffLJJ7r66qsVHh5udVl+yc3N1ezZs+V2uxUcHCyv1yuHw6H//u//tro0n73//vtatWqVFi1apFtuuUVff/21UlJSNHPmTKtL80tubq5efvll7du3T/Hx8XrjjTd07733BuT9E3/4wx+UkpKiK6+88qSvbdiwQXFxcRZU5T87fTaSVFRUpHnz5um9996Tw+HQsGHDlJaWFpAnF6677jolJycrKSlJPXv2bPG1P/3pT5o9e7ZFlfmnqqpKb775pi677DL16tVLq1at0tixY/WTn/zE6tJ8lpSUpN27d6tLly4KCwsL6L83iYmJWrdundVlnDHV1dX65ptvdMkll6impkbnnHOO1SWdEgH8NJSWlsrlcqm4uPiUXw+0I/iXXnpJN998s55++ulTfj1Qx4LFx8frkUceOenz+P4frkB05MiRgD2Ld9z//M//6L333lNjY6OuvPLKgL7h54svvtCRI0da3HwViJdrj7PTZ4P2Jzc3999+fezYsYYqOXOKiopOuTwQ/9488MADmjx5si3O5r/77rtKT09XY2OjXnrpJSUmJiorK0tXX3211aWdhCEopyEtLU3Lli3TrbfeKofD0eKPbiAe8dr1mKtTp06Kjo4O6MvnEydO/Lf1B+IlQenY7DTPPfecFi9erC+//FLp6emaN29eQA4XeuSRR7Rx40adf/75zcsC9XKtZK/PRpLeeecdLVmy5KQDpED6Pf39GV2+/zdn165dVpTlt/fee0+S9PXXX2vfvn2KjY1VcHCwtmzZoosuuiigAvhbb72la6+99gdn1QnEAP7VV18pKSlJLpdLISEhAX02/4knntCLL76ou+++Wy6XSytXrtQDDzxAAA9Uy5Ytk3Rsajg7+M1vfiPp2BF8IM7z+UN+9rOf6aabbtJVV13VYjaKQDqjP23aNElSTk6OOnTo0Hyj3/r161VXV2dxdf774x//2Pw59OnTR7/73e80Z84c/fWvf7W4Mt9t2bJFhYWFtpmT3U6fjSQ9+uijmjlzZkDPTnF8Rhe7OP53ZuLEiVq7dq06d+4s6diVvd///vdWluazTz75RNdee23zQcX3BdLBxHHPPPOM1SWcMU1NTS1mCbrooossrObfI4Cfhh8bwB+oIfZf//qXqqurA3L83an06NEj4IYDfd8VV1whSVqwYIFWr17dvHzQoEEBOVXXcTU1NYqJiWl+PWzYsOYbmQPN+eefb6urSHb6bKRjV8KuvfZaq8s4I8rLy7V27VpVV1e3eFjawoULrS7NLwcOHFBUVFTz6/DwcJWWllpYke/uu+8+Saf+u19bW2u6nDOiR48e+utf/6p//OMf8ng8GjJkiG699Vary/JLt27d9NZbb8nhcKiiokKrVq1qt7mAAH4ajociu3E4HLr22mt14YUXKiwsrHl5oF5KD6Qz3T+mrq5Oe/bs0YUXXijp2DABj8djcVX+69y5s/76179q9OjRkqT8/Hx16dLF4qr8c+655yohIUGXXXZZi4fVBOqBuJ0+G0n61a9+pfnz5+v//J//0+L3WiCO0b///vvVvXt3ffTRR7r++uu1adMm/eIXv7C6LL9dc801uv322zV8+HB5vV4VFBQoPj7e6rL8snHjRi1ZsqTFk6Rra2v17rvvWl2azxYuXKh9+/YpJSVFXq9Xr776qr755hvNmTPH6tJ89sgjjygzM1PfffedbrjhBl155ZWaN2+e1WWdEjdh+ujw4cPNTyc8/ij6oUOHWl2WX95///1TLg/UA47vj5uUjs3dvnnzZosq8t+WLVs0c+ZMde3aVV6vVwcPHtTjjz8esHO1FxcXa+7cuXr//fcVEhKiwYMH649//KO6detmdWk+W7NmzSmXJyUlGa7kzDjxswkNDVV0dHTAfjbSsWEO3xeoY/RHjBihwsJCLViwQCNGjNAFF1yg2267TWvXrrW6NL9t2LBB77//vhwOh4YOHapf//rXVpfklxtuuOGUD0tLT0+3ujSfjR49Wrm5uQoKCpIkeTweJSYmqqCgwOLKfPf3v/9dw4YNa7Hs9ddf1/Dhwy2q6IdxBtwHTz31lF544QV5PB516tRJJSUlGjBggF5++WWrS/PLhg0b9Mc//rHFsocffjhgA/iJ4yYbGhr05ptv6qOPPrKwIv9dffXV2rhxo/71r3/J4XDokksuafGAhEDTo0eP5nspAl1SUtIpD8QD1fHP5vDhwy2GBwSq9vjIaX8dn/nowgsv1O7duzVw4ECLK2q93r17q0uXLs3DuLZt2xaQVyfs9LC0xsZGeTye5it6jY2NAfdAu/z8fNXX1+vJJ59sHiYkHTuYWLZsGQE80K1Zs0abN29WZmampk6dqq+++kovvvii1WX5bM6cOfrmm2/06aef6osvvmhe7vF4AvrJnicKCQlRfHy8nnvuOatL8cvevXu1cuXKFpc3v/32W61atcrq0vxih5kpjrPbgfiuXbs0Y8YM1dbW6qWXXtKtt96qJUuWqH///laX5pePPvpIy5Yta/H/TnFxcUDeRD9kyBDdd999evjhh3XHHXdo586dAX3z79y5c/XWW2/ZYgYhOz0sLTExUZMmTVJCQoIk6bXXXmv+70BRXV2tDz74QNXV1S1ukA0ODtaMGTMsrOyHEcB94Ha7FRERob59+2r37t0aPny4Hn/8cavL8tnUqVNVVFSkzMzMFuOmg4OD1adPHwsra50T55r1er364osvAvas8QMPPKBrrrlGO3bsUFJSkt544w317dvX6rL8ZoeZKY6zy4H4cY8++qieeeYZPfjgg+ratav+4z/+QxkZGXrllVesLs0vs2fP1p133qk1a9Zo4sSJev3113XppZdaXZZfZsyYoa+//lo9e/bU448/ru3btwf0vS5///vfbTOD0P33368lS5Zo0aJFev755/XSSy8F7MOrpkyZoksvvVTvvvuuvF6vpkyZomuuucbqsnwybtw4jRs3Tu+++27ADAsOzHRikYiICOXm5qp///5auXKl3G53QN71/NOf/lQ//elPtXbtWh04cEBut1vbt2/X7t27A/asl6STpoXq1KmTlixZYlE1rdPQ0KD77rtPHo9Hl156qW666SalpKRYXZbf7DQzhV0OxI+rqalpceA9bNgwLViwwMKKWic0NFQpKSkqKipSx44dtXDhQiUmJlpdll+mTZump556SpI0YMAADRgwQLfddpv+67/+y+LK/GOnGYSuuOIKXXHFFTp8+LBeeOEFNTU1BdzD0k6cyzw8PFzXXXddi68F4tCg8PBwTZ06NSCugBHAfZCZmanXXntNY8eO1VtvvaX09HTdf//9Vpflt4yMDDU0NOiOO+7Qgw8+qGHDhunDDz9UVlaW1aX5JVBnoTiV8PBw1dfX62c/+5l27twZsDdfHmenmSnsciB+XFRUlHbv3t18ZWLt2rUBFyROFBYWpsOHD+vCCy/UP//5Tw0dOlSNjY1Wl+WTe++9V7t27VJJSUmLmxQbGxsD9uZYyV4zCO3evVt/+MMfVFJSIq/Xq969e2vhwoW64IILrC7ttD355JOSjk0u8c033+iyyy5TUFCQPvzwQ1188cX629/+ZnGFvgukK2DMguKDWbNmBeQvih+SnJys1atXNz+Sftq0aUpJSWkx/3QguOeee7Rs2TJdd911pxzeEIjjjFeuXKmNGzcqKytLN998s3r16qWmpib9+c9/tro0v9hpZoqSkhK99tpruuOOO/TYY49p69atuueeewJuzORxX3/9tR5++GF98skn6tChg3r16qVFixYF7JMwCwoKlJOTo6eeekrjxo1TUFCQ+vXrF1BXKaqqqnT48GFlZmYqLS2tebnT6VSXLl0CdmidnWYQSk5O1rRp05qv7L3xxhtasWJFQA5Hu/vuu5WWlqZevXpJOvaQvvT0dC1fvtziynw3duxY5ebm6sknn9TgwYN1xRVXKDExUfn5+VaXdhICuA9SUlL0l7/8xTYPrhkzZoxeffVVpaSkaO7cubr44ouVkpLSLn9Q/53jw2iKiopO+fVAfDSwdOyPcEREhPbv369PPvlEV199tcLDw60uCzZ19OhRNTU1KSIiwupSWu34o7SPHj2qvXv36uc//3nA33tgF3aZyjcpKemkA4rj4S/QJCQk6LXXXmt+7fV6NXLkyICchvDmm2/WsmXL9M4776ioqEhTpkxRXFycNmzYYHVpJwnMw2iLBAUF2erBNWPHjtXVV1+tyy+/XAMHDtTIkSN18803W12Wz9xut6SW49mO69Chg6qrq3XxxRebLqtVKioqtG7dOh0+fLh5zOTnn38esDdg2WlmihdeeEFLly49acagXbt2WVRR6xQVFSktLU1FRUVatWqVfve73+lPf/qTfvrTn1pdmk/s9MTiUz3TQPrfA4tA/Vmz0wxCV111lZYuXaqbbrpJwcHBys/PV58+fVRcXCxJ7fbpi6fSv39/Pfzww4qPj5fX69W6desCdtjjb3/7W82YMaP5Cti6des0YMAAq8s6Jc6A+8BuD66RpKampubJ98vLy9W5c2eLK/LftGnT9Nlnn+n666+XJG3atElut1tHjx5VYmKifvvb31pboA9uv/12RUZGnjRrSKAG8JEjR540Lq9Lly6aPXu21aX57LrrrtPKlSsD6g/sv3PnnXfq9ttv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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[26]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># the average price level of Airbnb w.r.t country</span>
<span class="n">airbnb_byprice_toplot</span><span class="o">.</span><span class="n">plot</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">x</span><span class="o">=</span><span class="s1">&#39;Country&#39;</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">&#39;Price&#39;</span><span class="p">)</span>
<span class="n">pp</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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y+Vy+R5HREQoPDxcJ0+eVOXKlfX5559bWF1g2rRpo3vuuUeJiYm2P1lbtWqVNm7cqCeffFLdu3fX4cOHNWLECCUlJVldmt+OHj2qpUuXKi8vT2cvYTFw4EALqwrcwIED1aFDB91www1Wl3LBhg0bprvuukuSlJWVpYcfflijR4/WnDlzLK7sXBdFcF67dq2WL1+ucePGqXfv3iosLNSECROsLisgp06d0uDBg1VSUqKbbrpJPXr0ULdu3awu64I888wz2rp1q+Lj433bXC6X/vnPf1pYVWDGjx+vcePGadasWerfv78++ugjFRYWWl1WwMaOHavLLrtM27ZtU3h4uPbs2aNRo0YpLS3N6tL8NmfOHGVnZ2vx4sXq27evrrzySiUmJur3v/+9IiMjrS7Pb055b3bs2CFJGjNmjG699VZ17txZLpdLy5cv1yeffGJxdYH54IMPtHz5cv3pT3/SoUOH1LVrV3Xu3NmWJ2vTpk1TamqqMjMz9bvf/U4pKSnq1auXLYPz008/rdjYWNWtW7fMyZpdValSxbah/+fy8/P16KOPaty4cUpMTFTXrl1DNgNcFME5Pj5ekZGRuu666/Ttt9+qY8eOOnbsmNVlBaRSpUoqLi7WNddco61bt+r222+3uqQLtn37dmVmZio8PNzqUi5YbGysmjRpoi+++ELHjh3T8OHD1aFDB6vLCtjWrVu1aNEi/d///Z8qVaqkiRMnKiEhweqyAlazZk117dpVEREReueddzRnzhxNnTpVzz77rFq3bm11eX5x2nvz9ddf68UXX/Q9btu2rV5//XULKwpcpUqV1LVrV3Xt2lUrVqzQSy+9pGnTpqlp06YaMWKEateubXWJfqlfv75ee+01de7cWb/5zW906tQpq0sKyMGDBzVr1iyrywiaxMRETZ06VU2aNFFExH/jnB0/rfV4PNqyZYs++ugjzZ07V9u3b1dpaanVZZ3XRRGcq1evrhkzZqhp06aaPHmypNMfc9pR586d1b9/f6Wlpem+++7TJ598ourVq1td1gVp2LChdu/erTp16lhdygWLiYnRzp07dd1112nDhg1q0qSJbf/ISKev/BcXF/uuzhw5csS2V2reffddLV68WLm5uerataveeust1ahRQzk5OUpMTLRdcHbSeyOdDpvvvfee2rdvL4/Ho8WLF+vSSy+1uqyA7N69W0uW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gbarM+9NXl5emY/S7SoUl9YN1JmZdK699lrt2LFDDRs2tLiiC1OnTh3FxcX5hjp9/vnntvwkwGkLVJWWlqqkpMT3CVppaantFhLLzMxUcXGxXn31Vd+QGun0ScCMGTMIzlZZtGiRVq9erdTUVA0YMEA//PCD3nrrLavL8svo0aP1448/asuWLfruu+9820tKSmy7CuL5REZGqn379vrrX/9qdSkB2bVrl+bOnVvmo8C9e/dq3rx5VpcWECfMdHCGk06gpdMrbg4dOlRFRUWaP3++HnroIb3yyitq0KCB1aUF5Msvv9SMGTPK/Ozs27fPljd3N2nSRIMHD9aIESPUt29fbd261bY3pb744otatWqVI2ajcdoCVQkJCerdu7c6duwoSXr//fd9/7aL48eP64svvtDx48fL3LwZHh6uoUOHWljZL7sognN8fLwqV66sunXraseOHWrTpo2mTJlidVl+GTBggLKzs5WamlpmTHB4eLiuu+46Cyu7cGfPF+r1evXdd9/Z9irtM888o7vvvlubNm1SYmKiVqxYobp161pdVsCcMNPBGU44gT7bSy+9pL/85S8aNmyYqlevrj/+8Y8aM2aMFixYYHVpARk1apQeffRRLVq0SL169dKHH36om266yeqyAjJ06FDt2bNHNWvW1JQpU7Rx40bb3svx6aefOmY2miFDhuiVV17R5MmT9cYbb2j+/Pm2XTBIkvr376+bbrpJ69atk9frVf/+/XX33XdbXZZf7r33Xt17771at26dbYbP2jOd+Kly5crKyMhQgwYNNHfuXMXHx9vuTtqrrrpKV111lZYsWaIDBw4oPj5eGzdu1I4dO2x7hemMn08RVK1aNb3yyisWVXNhTp06pcGDB6ukpEQ33XSTevTooW7dulldVsCcNNOBE06gz1ZYWFjmpLlZs2aaOHGihRVdmKioKHXr1k3Z2dmqUqWKJk2apISEBKvLCsigQYP02muvSZJuvvlm3XzzzXr44Yf1j3/8w+LK/Oek2WjuvPNO3XnnncrLy9Ps2bPl8XhsuUDV2fNRV6pUSa1atSrzNTsOo6lUqZIGDBhgi0+cLorgnJqaqvfff19du3bVqlWrlJKSoiFDhlhdVkDGjBmjU6dOqW/fvho2bJiaNWumzZs3Ky0tzerSAmbXWQ3Op1KlSiouLtY111yjrVu32vamwDOcNNOBE06gz1a1alXt2LHD90nAkiVLbBkCzoiOjlZeXp6uvfZaffXVV2ratKlKS0utLssvAwcO1Pbt25WTk1PmBrrS0lLb3rTppNloduzYoeeee045OTnyer2qU6eOJk2apKuvvtrq0vzy6quvSjo96cGPP/6oW265RWFhYdq8ebPq1aund955x+IK/WenT5wuilk1nn/+eVv+kJ9PUlKS3nvvPd/S24MGDVK3bt3KzB1sF0888YRmzJihVq1anXcYgB3H0c6dO1crV65UWlqa7rvvPtWuXVsej0dvvvmm1aUFxEkzHeTk5Oj9999X3759NWHCBK1du1ZPPPGE7cYEnrFnzx6NGDFC33zzjWJiYlS7dm1NnjzZtisHfvDBB0pPT9drr72me++9V2FhYapfv76tPhUoKChQXl6eUlNTlZyc7NseERGhuLg4Ww5Bc9JsNElJSRo0aJDvU7QVK1Zo1qxZth2y9fjjjys5OVm1a9eWdHqBtJSUFM2cOdPiyvzXtWtXZWRk6NVXX9Udd9yhO++8UwkJCcrMzLS6tHNcFMG5W7du+uc//+mIRUO6dOmihQsXqlu3bnrxxRdVr149devWLSS/uX7NmSEn2dnZ5/26XZdBLSgoUOXKlfXTTz/pm2++UfPmzVWpUiWry4JDnThxQh6PR5UrV7a6lAt2ZsngEydOaNeuXbrxxhttP7beCZwynWtiYuI5JwJnApsddezYUe+//77vsdfrVYcOHWw5Hd19992nGTNm6JNPPlF2drb69++vtm3bavny5VaXdg77nf4GICwszDGLhnTt2lXNmzfXrbfeqoYNG6pDhw667777rC4rIPHx8ZLKjtc6IyYmRsePH1e9evUquqwLcvToUS1dulR5eXm+cYHffvutbW8MctJMB7Nnz9b06dPPmYVm+/btFlV0YbKzs5WcnKzs7GzNmzdPTz75pF5++WVdddVVVpfmFyet8Hq+Oeml/54Q2PF7zUmz0dx1112aPn26evToofDwcGVmZuq6667Tvn37JClkV6r7JQ0aNNCIESPUvn17eb1eLV261LbDAx955BENHTrU94nT0qVLdfPNN1td1nldFFecnbZoiMfj8U14fvjwYV122WUWV3RhBg0apG3btukPf/iDJOnjjz9WfHy8Tpw4oYSEBD3yyCPWFuiHPn36KDY29pxZKOwanDt06HDOuLO4uDiNGjXK6tL81qpVK82dO9d2fxx/yaOPPqo+ffooLS1NixYt0rvvvqvFixfbburDXxoKcIYdhwQ4SatWrbRkyZJzZqN54403rC7Nb2duojvzu/ns+ONyuWw3PLC4uFhz5871ZZy77rpLDzzwgC2HBOXn56tKlSplPnGKjY0tMw1iqLDf/24AnLRoSK9evc57RcOOV8/PyM3N1aJFi1SlShVJp4N0//79NX/+fCUlJdkqOB88eFCzZs2yuoygcdJMB3Xq1NHll19udRlBc+TIETVv3lxpaWlyuVzq0aOH7UKzVDYY7927V99//72aN2+u/fv3h+QfzYuNU2ajWbVqlWbPnq2rr75aK1as0IIFC3TTTTfpySefVGRkpNXlBeTgwYNq166d2rVrJ+l0+D969KitLqbt379fXq9X/fr109/+9jffyUxsbKwef/xxZWVlWVzhuRwdnJ24aMigQYN8/y4pKdG//vUvX+C0qyNHjpQZfx4dHa38/HxFRETYbnzjjTfeqB07dqh+/fpWlxIUTpjp4IzevXsrISFBDRs2LLO6lp2GApwtJiZGP/30k+9nZOPGjWVmPbCbzMxMvf766yoqKtI777yj+++/X88995y6dOlidWkXNSfMRjNz5kxlZmZq4sSJ2rFjh4YPH67Ro0dr+/btmjx5si0/QZOkp556St99953q1avnWwPB7XYrPDxc48aNs8U49FdffVXr16/XgQMH9OCDD/q2R0REhOyc1I4eqrF3717foiFn3+F8ZtEQJyxTK52eQNyO483OmDJlijZv3qz27dvL4/Howw8/1G233aZrrrlGy5Yt09///nerSzSWmJioHTt2KC4uTtHR0b6xjXb7CPCMrKwszZ8/39YzHZzRpUsXtW7d+pybTu06FOCbb75RcnKy9uzZo6uvvlr5+fn685//bNvlnRMTEzVnzhw99NBDysjI0IEDB9SnT58yNz+h4jlhNprOnTtr/vz5qlSpktLS0rRv3z796U9/svXNdNLpBVAGDhzoGwv87bffatq0aRo1apQGDhxoq9m23njjDfXr18/qMow4+oqzExcNOXMTg/TfVfby8vIsrOjCDRs2TKtWrdKnn36q8PBwPfbYY2rZsqW+/PJL2wW0M9MEOkVMTIzefPNNuVwuvffee9q1a5dtr6ZHRUXZdqz5+Rw6dEgLFizQrl27VFpa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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Combine-airbnb-data-with-tourists-inflow-data">Combine airbnb data with tourists inflow data<a class="anchor-link" href="#Combine-airbnb-data-with-tourists-inflow-data">&#182;</a></h3>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[27]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">airbnb_travel</span> <span class="o">=</span> <span class="n">travel</span><span class="o">.</span><span class="n">drop</span><span class="p">([</span><span class="s1">&#39;2012&#39;</span><span class="p">,</span> <span class="s1">&#39;2013&#39;</span><span class="p">,</span> <span class="s1">&#39;2014&#39;</span><span class="p">,</span> <span class="s1">&#39;2016&#39;</span><span class="p">,</span> <span class="s1">&#39;2017&#39;</span><span class="p">],</span> <span class="c1">#only select data in 2015</span>
                <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span><span class="o">.</span><span class="n">merge</span><span class="p">(</span><span class="n">airbnb_byprice_toplot</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="s1">&#39;Country&#39;</span><span class="p">,</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">),</span> <span class="n">on</span><span class="o">=</span><span class="s1">&#39;Country Code&#39;</span><span class="p">)</span>
<span class="n">airbnb_travel</span><span class="o">.</span><span class="n">rename</span><span class="p">(</span><span class="n">columns</span><span class="o">=</span><span class="p">{</span><span class="s1">&#39;2015&#39;</span><span class="p">:</span> <span class="s1">&#39;TouristsInflow&#39;</span><span class="p">},</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="n">airbnb_travel</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[27]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country Name</th>
      <th>Country Code</th>
      <th>Region</th>
      <th>IncomeGroup</th>
      <th>TouristsInflow</th>
      <th>Price</th>
      <th>Count</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Australia</td>
      <td>AUS</td>
      <td>East Asia &amp; Pacific</td>
      <td>High income</td>
      <td>7450000.0</td>
      <td>165.077177</td>
      <td>40219</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Austria</td>
      <td>AUT</td>
      <td>Europe &amp; Central Asia</td>
      <td>High income</td>
      <td>26728000.0</td>
      <td>67.076562</td>
      <td>7889</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Belgium</td>
      <td>BEL</td>
      <td>Europe &amp; Central Asia</td>
      <td>High income</td>
      <td>8355000.0</td>
      <td>68.052057</td>
      <td>7415</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Canada</td>
      <td>CAN</td>
      <td>North America</td>
      <td>High income</td>
      <td>17971000.0</td>
      <td>107.010622</td>
      <td>30692</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Germany</td>
      <td>DEU</td>
      <td>Europe &amp; Central Asia</td>
      <td>High income</td>
      <td>34970000.0</td>
      <td>57.222044</td>
      <td>20568</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Spain</td>
      <td>ESP</td>
      <td>Europe &amp; Central Asia</td>
      <td>High income</td>
      <td>68175000.0</td>
      <td>97.136425</td>
      <td>45732</td>
    </tr>
    <tr>
      <th>6</th>
      <td>France</td>
      <td>FRA</td>
      <td>Europe &amp; Central Asia</td>
      <td>High income</td>
      <td>84452000.0</td>
      <td>94.431201</td>
      <td>56505</td>
    </tr>
    <tr>
      <th>7</th>
      <td>United Kingdom</td>
      <td>GBR</td>
      <td>Europe &amp; Central Asia</td>
      <td>High income</td>
      <td>34436000.0</td>
      <td>93.020880</td>
      <td>60966</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Greece</td>
      <td>GRC</td>
      <td>Europe &amp; Central Asia</td>
      <td>High income</td>
      <td>23599000.0</td>
      <td>52.935767</td>
      <td>5122</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Ireland</td>
      <td>IRL</td>
      <td>Europe &amp; Central Asia</td>
      <td>High income</td>
      <td>9528000.0</td>
      <td>103.780488</td>
      <td>6724</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Italy</td>
      <td>ITA</td>
      <td>Europe &amp; Central Asia</td>
      <td>High income</td>
      <td>50732000.0</td>
      <td>93.964180</td>
      <td>33110</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Netherlands</td>
      <td>NLD</td>
      <td>Europe &amp; Central Asia</td>
      <td>High income</td>
      <td>15007000.0</td>
      <td>133.993607</td>
      <td>15173</td>
    </tr>
    <tr>
      <th>12</th>
      <td>United States</td>
      <td>USA</td>
      <td>North America</td>
      <td>High income</td>
      <td>77774000.0</td>
      <td>156.051199</td>
      <td>132581</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Dataset-of-hotels">Dataset of hotels<a class="anchor-link" href="#Dataset-of-hotels">&#182;</a></h2><p>There are a lot of problems when we read this dataset. The data is not trivially writen in Comma Seperated Value. It contains quotation and semicolon. Another problem is some values in the column latitude are mixed in the url data.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[28]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">hotels_rawdata</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s1">&#39;hotels.csv&#39;</span><span class="p">,</span> <span class="n">sep</span><span class="o">=</span><span class="s1">&#39;;&#39;</span><span class="p">,</span> <span class="n">quoting</span><span class="o">=</span><span class="n">csv</span><span class="o">.</span><span class="n">QUOTE_NONE</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stderr output_text">
<pre>/Users/Hope/anaconda3/lib/python3.7/site-packages/IPython/core/interactiveshell.py:3020: DtypeWarning:

Columns (9) have mixed types. Specify dtype option on import or set low_memory=False.

</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[29]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">hotels_rawdata</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[29]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>"hotelName</th>
      <th>stars</th>
      <th>price</th>
      <th>cityName</th>
      <th>countryCode</th>
      <th>countryName</th>
      <th>address</th>
      <th>location</th>
      <th>url</th>
      <th>latitude</th>
      <th>longitude"</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>"Fafa Island Resort</td>
      <td>3.0</td>
      <td>172</td>
      <td>NukuAlofa</td>
      <td>TO</td>
      <td>Tonga</td>
      <td>Fafa Island PO Box 1444</td>
      <td>NukuAlofa Tonga</td>
      <td>NaN</td>
      <td>-21.0862</td>
      <td>-175.16"</td>
    </tr>
    <tr>
      <th>1</th>
      <td>"International Dateline Hotel</td>
      <td>3.0</td>
      <td>99999</td>
      <td>NukuAlofa</td>
      <td>TO</td>
      <td>Tonga</td>
      <td>P.O.Box 39 Vuna Road</td>
      <td>NukuAlofa Tonga</td>
      <td>http://www.datelinehotel.com/</td>
      <td>-21.1263</td>
      <td>-175.213"</td>
    </tr>
    <tr>
      <th>2</th>
      <td>"Kava Palm Guesthouse NukuAlofa</td>
      <td>2.0</td>
      <td>99999</td>
      <td>NukuAlofa</td>
      <td>TO</td>
      <td>Tonga</td>
      <td>Taufaa ahau Road</td>
      <td>NukuAlofa Tonga</td>
      <td>NaN</td>
      <td>-21.1599</td>
      <td>-175.229"</td>
    </tr>
    <tr>
      <th>3</th>
      <td>"Lagoon Lodge Nuku‘alofa</td>
      <td>3.0</td>
      <td>99</td>
      <td>NukuAlofa</td>
      <td>TO</td>
      <td>Tonga</td>
      <td>Umusi Road Fanga’uta Lagoon Ma’ufanga</td>
      <td>NukuAlofa Tonga</td>
      <td>NaN</td>
      <td>-21.153</td>
      <td>-175.231"</td>
    </tr>
    <tr>
      <th>4</th>
      <td>"Likualofa Beach Resort</td>
      <td>3.0</td>
      <td>105</td>
      <td>Kanokupolu</td>
      <td>TO</td>
      <td>Tonga</td>
      <td>Private Bag No.2</td>
      <td>Kanokupolu Tonga</td>
      <td>NaN</td>
      <td>-21.0822</td>
      <td>-175.345"</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[30]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">hotels_raw</span> <span class="o">=</span> <span class="n">hotels_rawdata</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="s1">&#39;url&#39;</span><span class="p">,</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>

<span class="c1"># remove the quotation mark in first and last columns</span>
<span class="n">hotels_raw</span><span class="o">.</span><span class="n">rename</span><span class="p">(</span><span class="n">columns</span><span class="o">=</span><span class="p">{</span><span class="s1">&#39;&quot;hotelName&#39;</span><span class="p">:</span> <span class="s1">&#39;hotelName&#39;</span><span class="p">,</span> <span class="s1">&#39;longitude&quot;&#39;</span><span class="p">:</span> <span class="s1">&#39;longitude&#39;</span><span class="p">},</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="n">hotels_raw</span><span class="p">[</span><span class="s1">&#39;hotelName&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">hotels_raw</span><span class="p">[</span><span class="s1">&#39;hotelName&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">str</span><span class="o">.</span><span class="n">replace</span><span class="p">(</span><span class="s1">&#39;&quot;&#39;</span><span class="p">,</span> <span class="s1">&#39;&#39;</span><span class="p">)</span>
<span class="n">hotels_raw</span><span class="p">[</span><span class="s1">&#39;longitude&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">hotels_raw</span><span class="p">[</span><span class="s1">&#39;longitude&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">str</span><span class="o">.</span><span class="n">replace</span><span class="p">(</span><span class="s1">&#39;&quot;&#39;</span><span class="p">,</span> <span class="s1">&#39;&#39;</span><span class="p">)</span>

<span class="c1"># 2-letter country codes cannot be recognized by plotly</span>
<span class="c1"># so we turn it into 3-letter codes</span>
<span class="n">hotels</span> <span class="o">=</span> <span class="n">countrycode2to3</span><span class="p">(</span><span class="n">hotels_raw</span><span class="p">,</span> <span class="n">on</span><span class="o">=</span><span class="s1">&#39;countryName&#39;</span><span class="p">,</span> <span class="n">code</span><span class="o">=</span><span class="s1">&#39;countryCode&#39;</span><span class="p">)</span>

<span class="c1"># remove the NA type value of price==99999</span>
<span class="n">hotels</span> <span class="o">=</span> <span class="n">hotels</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">hotels</span><span class="o">.</span><span class="n">price</span> <span class="o">!=</span> <span class="mi">99999</span><span class="p">,</span> <span class="p">:]</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[31]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">convertNum</span><span class="p">(</span><span class="n">x</span><span class="p">):</span>
    <span class="k">try</span><span class="p">:</span>
        <span class="k">return</span> <span class="n">np</span><span class="o">.</span><span class="n">float</span><span class="p">(</span><span class="n">x</span><span class="p">)</span>
    <span class="k">except</span><span class="p">:</span>
        <span class="nb">print</span><span class="p">(</span><span class="n">x</span><span class="p">)</span>
        <span class="k">return</span> <span class="n">np</span><span class="o">.</span><span class="n">nan</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[32]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">hotels</span><span class="p">[</span><span class="s1">&#39;latitude&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">hotels</span><span class="p">[</span><span class="s1">&#39;latitude&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="n">convertNum</span><span class="p">)</span>
<span class="n">hotels</span><span class="p">[</span><span class="s1">&#39;longitude&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">hotels</span><span class="p">[</span><span class="s1">&#39;longitude&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="n">convertNum</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>/Hotel_Review-g293748-d305494-Reviews-Hotel_Sea_Cliff-Dar_es_Salaam.html
/Hotel_Review-g187497-d1153245-Reviews-ME_Barcelona-Barcelona_Catalonia.html
/Hotel_Review-g295371-d2522505-Reviews-Guest_House_Brigita-Dubrovnik_Dubrovnik_Neretva_County_Dalmatia.html
/Hotel_Review-g297586-d1145840-Reviews-Hotel_Padmini_Residency-Hyderabad_Andhra_Pradesh.html
/Hotel_Review-g304555-d1142637-Reviews-Maxima_Resort-Jaipur_Rajasthan.html
/Hotel_Review-g294212-d1159881-Reviews-Jianguo_Hotel-Beijing.html
/Hotel_Review-g303148-d1116545-Reviews-Hotel_Yamaki-Hamamatsu_Shizuoka_Prefecture_Chubu.html
/Hotel_Review-g298031-d1012164-Reviews-Nazar_Garden_Hotel-Fethiye_Mugla_Province_Turkish_Aegean_Coast.html
/VacationRentals-g298019-Reviews-Mugla_Province_Turkish_Aegean_Coast-Vacation_Rentals.html
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[33]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">hotels</span> <span class="o">=</span> <span class="n">hotels</span><span class="o">.</span><span class="n">dropna</span><span class="p">(</span><span class="n">subset</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;stars&#39;</span><span class="p">,</span> <span class="s1">&#39;price&#39;</span><span class="p">,</span> <span class="s1">&#39;latitude&#39;</span><span class="p">,</span> <span class="s1">&#39;longitude&#39;</span><span class="p">])</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[34]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">hotels</span><span class="o">.</span><span class="n">countryCode</span><span class="o">.</span><span class="n">unique</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[34]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>array([&#39;TON&#39;, &#39;FJI&#39;, &#39;WSM&#39;, &#39;ARG&#39;, &#39;CHL&#39;, &#39;NZL&#39;, &#39;AUS&#39;, &#39;URY&#39;, &#39;ZAF&#39;,
       &#39;BRA&#39;, &#39;LSO&#39;, &#39;PRY&#39;, &#39;NAM&#39;, &#39;MOZ&#39;, &#39;MDG&#39;, &#39;BWA&#39;, &#39;PYF&#39;, &#39;PRT&#39;,
       &#39;ZWE&#39;, &#39;NCL&#39;, &#39;BOL&#39;, &#39;MUS&#39;, &#39;VUT&#39;, &#39;ZMB&#39;, &#39;PER&#39;, &#39;MWI&#39;, &#39;ASM&#39;,
       &#39;AGO&#39;, &#39;IDN&#39;, &#39;PNG&#39;, &#39;SLB&#39;, &#39;TZA&#39;, &#39;SYC&#39;, &#39;ECU&#39;, &#39;COL&#39;, &#39;KEN&#39;,
       &#39;BDI&#39;, &#39;RWA&#39;, &#39;NLD&#39;, &#39;MEX&#39;, &#39;ITA&#39;, &#39;HRV&#39;, &#39;GAB&#39;, &#39;UGA&#39;, &#39;MDV&#39;,
       &#39;GNQ&#39;, &#39;MYS&#39;, &#39;SGP&#39;, &#39;CMR&#39;, &#39;GUY&#39;, &#39;SUR&#39;, &#39;GHA&#39;, &#39;NGA&#39;, &#39;LKA&#39;,
       &#39;PHL&#39;, &#39;TGO&#39;, &#39;BEN&#39;, &#39;THA&#39;, &#39;PAN&#39;, &#39;PLW&#39;, &#39;CRI&#39;, &#39;ETH&#39;, &#39;IND&#39;,
       &#39;VNM&#39;, &#39;GIN&#39;, &#39;KHM&#39;, &#39;NIC&#39;, &#39;GRD&#39;, &#39;BFA&#39;, &#39;DJI&#39;, &#39;ABW&#39;, &#39;SEN&#39;,
       &#39;MLI&#39;, &#39;TCD&#39;, &#39;GTM&#39;, &#39;SLV&#39;, &#39;BRB&#39;, &#39;GUM&#39;, &#39;HND&#39;, &#39;MNP&#39;, &#39;DMA&#39;,
       &#39;BLZ&#39;, &#39;SAU&#39;, &#39;OMN&#39;, &#39;MMR&#39;, &#39;JAM&#39;, &#39;DOM&#39;, &#39;PRI&#39;, &#39;HTI&#39;, &#39;MRT&#39;,
       &#39;CHN&#39;, &#39;USA&#39;, &#39;CYM&#39;, &#39;CUB&#39;, &#39;TCA&#39;, &#39;BGD&#39;, &#39;ARE&#39;, &#39;QAT&#39;, &#39;PAK&#39;,
       &#39;JPN&#39;, &#39;BHR&#39;, &#39;ESP&#39;, &#39;NPL&#39;, &#39;BTN&#39;, &#39;KWT&#39;, &#39;MAR&#39;, &#39;ISR&#39;, &#39;JOR&#39;,
       &#39;BMU&#39;, &#39;TUN&#39;, &#39;LBY&#39;, &#39;DZA&#39;, &#39;LBN&#39;, &#39;GRC&#39;, &#39;CYP&#39;, &#39;AFG&#39;, &#39;MLT&#39;,
       &#39;GIB&#39;, &#39;TUR&#39;, &#39;TJK&#39;, &#39;ALB&#39;, &#39;ARM&#39;, &#39;AZE&#39;, &#39;UZB&#39;, &#39;CAN&#39;, &#39;FRA&#39;,
       &#39;MNE&#39;, &#39;BGR&#39;, &#39;GEO&#39;, &#39;AND&#39;, &#39;XKX&#39;, &#39;SRB&#39;, &#39;KAZ&#39;, &#39;MCO&#39;, &#39;SMR&#39;,
       &#39;ROU&#39;, &#39;UKR&#39;, &#39;CHE&#39;, &#39;SVN&#39;, &#39;HUN&#39;, &#39;AUT&#39;, &#39;MDA&#39;, &#39;DEU&#39;, &#39;LIE&#39;,
       &#39;MNG&#39;, &#39;CZE&#39;, &#39;GBR&#39;, &#39;BEL&#39;, &#39;LUX&#39;, &#39;POL&#39;, &#39;IRL&#39;, &#39;BLR&#39;, &#39;LTU&#39;,
       &#39;DNK&#39;, &#39;SWE&#39;, &#39;LVA&#39;, &#39;EST&#39;, &#39;NOR&#39;, &#39;FIN&#39;, &#39;GRL&#39;, &#39;FRO&#39;, &#39;ISL&#39;],
      dtype=object)</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[35]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">hotels</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[35]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>hotelName</th>
      <th>stars</th>
      <th>price</th>
      <th>cityName</th>
      <th>countryName</th>
      <th>address</th>
      <th>location</th>
      <th>latitude</th>
      <th>longitude</th>
      <th>countryCode</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Fafa Island Resort</td>
      <td>3.0</td>
      <td>172</td>
      <td>NukuAlofa</td>
      <td>Tonga</td>
      <td>Fafa Island PO Box 1444</td>
      <td>NukuAlofa Tonga</td>
      <td>-21.0862</td>
      <td>-175.160</td>
      <td>TON</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Lagoon Lodge Nuku‘alofa</td>
      <td>3.0</td>
      <td>99</td>
      <td>NukuAlofa</td>
      <td>Tonga</td>
      <td>Umusi Road Fanga’uta Lagoon Ma’ufanga</td>
      <td>NukuAlofa Tonga</td>
      <td>-21.1530</td>
      <td>-175.231</td>
      <td>TON</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Likualofa Beach Resort</td>
      <td>3.0</td>
      <td>105</td>
      <td>Kanokupolu</td>
      <td>Tonga</td>
      <td>Private Bag No.2</td>
      <td>Kanokupolu Tonga</td>
      <td>-21.0822</td>
      <td>-175.345</td>
      <td>TON</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Little Italy Hotel NukuAlofa</td>
      <td>5.0</td>
      <td>152</td>
      <td>NukuAlofa</td>
      <td>Tonga</td>
      <td>P.O.Box 2891 Vuna Road Kolomotua</td>
      <td>NukuAlofa Tonga</td>
      <td>-21.1343</td>
      <td>-175.196</td>
      <td>TON</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Loumaile Lodge</td>
      <td>4.0</td>
      <td>168</td>
      <td>NukuAlofa</td>
      <td>Tonga</td>
      <td>Taufa’ahau Road</td>
      <td>NukuAlofa Tonga</td>
      <td>-21.1361</td>
      <td>-175.202</td>
      <td>TON</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[36]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">hotels_forcity</span> <span class="o">=</span> <span class="n">hotels</span><span class="o">.</span><span class="n">drop</span><span class="p">([</span><span class="s1">&#39;hotelName&#39;</span><span class="p">,</span><span class="s1">&#39;address&#39;</span><span class="p">,</span> <span class="s1">&#39;location&#39;</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[37]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">hotels_forcity</span><span class="o">.</span><span class="n">head</span><span class="p">(</span><span class="mi">10</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[37]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>stars</th>
      <th>price</th>
      <th>cityName</th>
      <th>countryName</th>
      <th>latitude</th>
      <th>longitude</th>
      <th>countryCode</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>3.0</td>
      <td>172</td>
      <td>NukuAlofa</td>
      <td>Tonga</td>
      <td>-21.0862</td>
      <td>-175.160</td>
      <td>TON</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3.0</td>
      <td>99</td>
      <td>NukuAlofa</td>
      <td>Tonga</td>
      <td>-21.1530</td>
      <td>-175.231</td>
      <td>TON</td>
    </tr>
    <tr>
      <th>4</th>
      <td>3.0</td>
      <td>105</td>
      <td>Kanokupolu</td>
      <td>Tonga</td>
      <td>-21.0822</td>
      <td>-175.345</td>
      <td>TON</td>
    </tr>
    <tr>
      <th>5</th>
      <td>5.0</td>
      <td>152</td>
      <td>NukuAlofa</td>
      <td>Tonga</td>
      <td>-21.1343</td>
      <td>-175.196</td>
      <td>TON</td>
    </tr>
    <tr>
      <th>6</th>
      <td>4.0</td>
      <td>168</td>
      <td>NukuAlofa</td>
      <td>Tonga</td>
      <td>-21.1361</td>
      <td>-175.202</td>
      <td>TON</td>
    </tr>
    <tr>
      <th>11</th>
      <td>4.0</td>
      <td>173</td>
      <td>NukuAlofa</td>
      <td>Tonga</td>
      <td>-21.1237</td>
      <td>-175.223</td>
      <td>TON</td>
    </tr>
    <tr>
      <th>12</th>
      <td>0.0</td>
      <td>132</td>
      <td>Kanokupolu</td>
      <td>Tonga</td>
      <td>-21.0740</td>
      <td>-175.338</td>
      <td>TON</td>
    </tr>
    <tr>
      <th>13</th>
      <td>3.0</td>
      <td>169</td>
      <td>NukuAlofa</td>
      <td>Tonga</td>
      <td>-21.1263</td>
      <td>-175.213</td>
      <td>TON</td>
    </tr>
    <tr>
      <th>14</th>
      <td>4.0</td>
      <td>149</td>
      <td>Lotofoa</td>
      <td>Tonga</td>
      <td>-19.7236</td>
      <td>-174.286</td>
      <td>TON</td>
    </tr>
    <tr>
      <th>19</th>
      <td>3.0</td>
      <td>197</td>
      <td>Waiyevo</td>
      <td>Fiji</td>
      <td>-16.7833</td>
      <td>-179.983</td>
      <td>FJI</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[38]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># hotels data grouped by city</span>
<span class="n">hotels_city</span> <span class="o">=</span> <span class="n">hotels_forcity</span><span class="o">.</span><span class="n">groupby</span><span class="p">([</span><span class="s1">&#39;cityName&#39;</span><span class="p">,</span> <span class="s1">&#39;countryName&#39;</span><span class="p">,</span> <span class="s1">&#39;countryCode&#39;</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="mi">0</span><span class="p">)</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span>
<span class="n">hotels_city</span><span class="p">[</span><span class="s1">&#39;count&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">hotels_forcity</span><span class="o">.</span><span class="n">groupby</span><span class="p">([</span><span class="s1">&#39;cityName&#39;</span><span class="p">,</span> <span class="s1">&#39;countryName&#39;</span><span class="p">,</span> <span class="s1">&#39;countryCode&#39;</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="mi">0</span><span class="p">)</span><span class="o">.</span><span class="n">count</span><span class="p">()[</span><span class="s1">&#39;price&#39;</span><span class="p">]</span>
<span class="n">hotels_city</span> <span class="o">=</span> <span class="n">hotels_city</span><span class="o">.</span><span class="n">reset_index</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[39]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">hotels_city</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[39]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>cityName</th>
      <th>countryName</th>
      <th>countryCode</th>
      <th>stars</th>
      <th>price</th>
      <th>latitude</th>
      <th>longitude</th>
      <th>count</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>100 Mile House</td>
      <td>Canada</td>
      <td>CAN</td>
      <td>2.50000</td>
      <td>97.50000</td>
      <td>51.630200</td>
      <td>-121.300500</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>108 Mile Ranch</td>
      <td>Canada</td>
      <td>CAN</td>
      <td>4.00000</td>
      <td>183.00000</td>
      <td>51.733600</td>
      <td>-121.330000</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>A Arnoia</td>
      <td>Spain</td>
      <td>ESP</td>
      <td>3.00000</td>
      <td>90.00000</td>
      <td>42.253200</td>
      <td>-8.135950</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>A Capela</td>
      <td>Spain</td>
      <td>ESP</td>
      <td>3.00000</td>
      <td>133.00000</td>
      <td>43.430200</td>
      <td>-8.063450</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>A Coruna</td>
      <td>Spain</td>
      <td>ESP</td>
      <td>2.65625</td>
      <td>50.21875</td>
      <td>43.358356</td>
      <td>-8.408819</td>
      <td>32</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[40]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">worldscatter</span><span class="p">(</span><span class="n">hotels</span><span class="p">):</span>
    <span class="c1">#data</span>
    <span class="n">data</span> <span class="o">=</span> <span class="p">[</span><span class="nb">dict</span><span class="p">(</span><span class="nb">type</span><span class="o">=</span><span class="s1">&#39;scattergeo&#39;</span><span class="p">,</span>
                 <span class="n">lat</span><span class="o">=</span><span class="n">hotels</span><span class="p">[</span><span class="s1">&#39;latitude&#39;</span><span class="p">],</span>
                 <span class="n">lon</span><span class="o">=</span><span class="n">hotels</span><span class="p">[</span><span class="s1">&#39;longitude&#39;</span><span class="p">],</span>
                 <span class="n">marker</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span>
                     <span class="n">autocolorscale</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span> 
                     <span class="n">cmax</span><span class="o">=</span><span class="mi">300</span><span class="p">,</span> 
                     <span class="n">cmin</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span> 
                     <span class="n">color</span><span class="o">=</span> <span class="n">hotels</span><span class="p">[</span><span class="s1">&#39;price&#39;</span><span class="p">],</span>
                     <span class="n">colorbar</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">title</span><span class="o">=</span><span class="s2">&quot;Price&quot;</span><span class="p">),</span> 
                     <span class="n">colorscale</span><span class="o">=</span><span class="n">scale2</span><span class="p">,</span> 
                     <span class="n">opacity</span><span class="o">=</span><span class="n">hotels</span><span class="p">[</span><span class="s1">&#39;price&#39;</span><span class="p">]</span><span class="o">/</span><span class="mi">200</span><span class="p">,</span> 
                     <span class="n">size</span><span class="o">=</span><span class="mi">8</span>
                 <span class="p">),</span>

                 <span class="n">text</span><span class="o">=</span><span class="p">(</span><span class="s1">&#39;City: &#39;</span> <span class="o">+</span> <span class="n">hotels</span><span class="p">[</span><span class="s1">&#39;cityName&#39;</span><span class="p">]</span> <span class="o">+</span> 
                       <span class="s1">&#39;&lt;br&gt;Country: &#39;</span> <span class="o">+</span> <span class="n">hotels</span><span class="p">[</span><span class="s1">&#39;countryName&#39;</span><span class="p">]</span> <span class="o">+</span>
                       <span class="s1">&#39;&lt;br&gt;Price: $&#39;</span> <span class="o">+</span> <span class="n">hotels</span><span class="p">[</span><span class="s1">&#39;price&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="nb">str</span><span class="p">)),</span>
                 <span class="n">mode</span><span class="o">=</span><span class="s1">&#39;markers&#39;</span><span class="p">,</span>
                <span class="p">)]</span>
    
    <span class="c1">#layout</span>
    <span class="n">layout</span> <span class="o">=</span> <span class="nb">dict</span><span class="p">(</span><span class="n">showlegend</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span>
                  <span class="n">title</span><span class="o">=</span> <span class="s1">&#39;Hotel Price by City&#39;</span> <span class="o">+</span> <span class="s1">&#39;&lt;br&gt; Hover for value&#39;</span><span class="p">,</span>
                  <span class="n">autosize</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span>
                  <span class="n">hovermode</span><span class="o">=</span><span class="s1">&#39;closest&#39;</span><span class="p">,</span>
<span class="c1">#                   mapbox=dict(accesstoken=&#39;pk.eyJ1IjoidmVubGFoIiwiYSI6ImNqZ2dlMXl5ajVhbWMyd2tsNjFmNHMxMzYifQ.uatR8hT0ddRPxvEyt8CI9g&#39;,</span>
<span class="c1">#                               bearing=0,</span>
<span class="c1">#                               center=dict(lat=str(hotels.latitude.mean()),</span>
<span class="c1">#                                           lon=str(hotels.longitude.mean())</span>
<span class="c1">#                               )</span>
<span class="c1">#                   ),</span>
                  <span class="n">pitch</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span>
                  <span class="n">style</span><span class="o">=</span><span class="s1">&#39;light&#39;</span><span class="p">,</span>
                  <span class="n">zoom</span><span class="o">=</span><span class="mi">3</span><span class="p">,</span>
                  <span class="n">geo</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">projection</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="nb">type</span><span class="o">=</span><span class="s1">&#39;orthographic&#39;</span><span class="p">),</span> <span class="c1">#Mercator</span>
                           <span class="n">scope</span><span class="o">=</span><span class="s1">&#39;world&#39;</span><span class="p">,</span>
                           <span class="n">showlakes</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span>
                           <span class="n">showland</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span>
                           <span class="n">lakecolor</span><span class="o">=</span><span class="s1">&#39;rgb(95,145,237)&#39;</span><span class="p">,</span>
                           <span class="n">landcolor</span><span class="o">=</span><span class="s1">&#39;rgb(220,220,220)&#39;</span><span class="p">,</span>
                          <span class="p">)</span>
                 <span class="p">)</span>
    
    <span class="n">fig</span> <span class="o">=</span> <span class="nb">dict</span><span class="p">(</span><span class="n">data</span><span class="o">=</span><span class="n">data</span><span class="p">,</span> <span class="n">layout</span><span class="o">=</span><span class="n">layout</span><span class="p">)</span>
    <span class="k">return</span> <span class="n">py</span><span class="o">.</span><span class="n">iplot</span><span class="p">(</span><span class="n">fig</span><span class="p">,</span> <span class="n">validate</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span> <span class="n">filename</span><span class="o">=</span><span class="s1">&#39;scatterhotels&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[41]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#only plot the city with more than 10 hotels</span>
<span class="n">hotels_cityover10</span> <span class="o">=</span> <span class="n">hotels_city</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">hotels_city</span><span class="p">[</span><span class="s1">&#39;count&#39;</span><span class="p">]</span> <span class="o">&gt;</span> <span class="mi">10</span><span class="p">,</span> <span class="p">:]</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[42]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">hotels_cityover10</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[42]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>cityName</th>
      <th>countryName</th>
      <th>countryCode</th>
      <th>stars</th>
      <th>price</th>
      <th>latitude</th>
      <th>longitude</th>
      <th>count</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>4</th>
      <td>A Coruna</td>
      <td>Spain</td>
      <td>ESP</td>
      <td>2.656250</td>
      <td>50.218750</td>
      <td>43.358356</td>
      <td>-8.408819</td>
      <td>32</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Aachen</td>
      <td>Germany</td>
      <td>DEU</td>
      <td>3.073529</td>
      <td>85.882353</td>
      <td>50.764356</td>
      <td>6.100683</td>
      <td>34</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Aalborg</td>
      <td>Denmark</td>
      <td>DNK</td>
      <td>3.142857</td>
      <td>117.571429</td>
      <td>57.042714</td>
      <td>9.917925</td>
      <td>14</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Aarhus</td>
      <td>Denmark</td>
      <td>DNK</td>
      <td>2.950000</td>
      <td>133.100000</td>
      <td>56.091285</td>
      <td>10.207155</td>
      <td>20</td>
    </tr>
    <tr>
      <th>30</th>
      <td>Abano Terme</td>
      <td>Italy</td>
      <td>ITA</td>
      <td>3.781250</td>
      <td>92.468750</td>
      <td>45.352228</td>
      <td>11.781609</td>
      <td>32</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[43]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">worldscatter</span><span class="p">(</span><span class="n">hotels_cityover10</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stderr output_text">
<pre>/Users/Hope/anaconda3/lib/python3.7/site-packages/IPython/core/display.py:689: UserWarning:

Consider using IPython.display.IFrame instead

</pre>
</div>
</div>

<div class="output_area">

    <div class="prompt output_prompt">Out[43]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<iframe id="igraph" scrolling="no" style="border:none;" seamless="seamless" src="https://plot.ly/~ghuang920/44.embed" height="525px" width="100%"></iframe>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Combine-Airbnb,-Hotels,-Tourists-Inflow-three-datasets-together">Combine Airbnb, Hotels, Tourists Inflow three datasets together<a class="anchor-link" href="#Combine-Airbnb,-Hotels,-Tourists-Inflow-three-datasets-together">&#182;</a></h2>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[44]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># hotels grouped by country</span>
<span class="n">hotels_bycountry</span> <span class="o">=</span> <span class="n">hotels_city</span><span class="o">.</span><span class="n">drop</span><span class="p">([</span><span class="s1">&#39;latitude&#39;</span><span class="p">,</span><span class="s1">&#39;longitude&#39;</span><span class="p">,</span> <span class="s1">&#39;count&#39;</span><span class="p">]</span>
                     <span class="p">,</span><span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span><span class="o">.</span><span class="n">groupby</span><span class="p">([</span><span class="s1">&#39;countryName&#39;</span><span class="p">,</span> <span class="s1">&#39;countryCode&#39;</span><span class="p">])</span><span class="o">.</span><span class="n">mean</span><span class="p">(</span><span class="n">numeric_only</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="n">hotels_bycountry</span><span class="p">[</span><span class="s1">&#39;count&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">hotels_city</span><span class="o">.</span><span class="n">drop</span><span class="p">([</span><span class="s1">&#39;latitude&#39;</span><span class="p">,</span><span class="s1">&#39;longitude&#39;</span><span class="p">,</span> <span class="s1">&#39;stars&#39;</span><span class="p">,</span> <span class="s1">&#39;price&#39;</span><span class="p">]</span>
                              <span class="p">,</span><span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span><span class="o">.</span><span class="n">groupby</span><span class="p">([</span><span class="s1">&#39;countryName&#39;</span><span class="p">,</span> <span class="s1">&#39;countryCode&#39;</span><span class="p">])</span><span class="o">.</span><span class="n">sum</span><span class="p">()</span>
<span class="n">hotels_bycountry</span> <span class="o">=</span> <span class="n">hotels_bycountry</span><span class="o">.</span><span class="n">reset_index</span><span class="p">()</span><span class="o">.</span><span class="n">drop</span><span class="p">([</span><span class="s1">&#39;countryName&#39;</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
<span class="n">hotels_bycountry</span> <span class="o">=</span> <span class="n">hotels_bycountry</span><span class="o">.</span><span class="n">rename</span><span class="p">(</span><span class="n">columns</span><span class="o">=</span><span class="p">{</span><span class="s1">&#39;countryCode&#39;</span><span class="p">:</span> <span class="s1">&#39;Country Code&#39;</span><span class="p">})</span>

<span class="c1"># Combine hotels data into the previous two datasets</span>
<span class="n">airbnb_hotels_travel</span> <span class="o">=</span> <span class="n">airbnb_travel</span><span class="o">.</span><span class="n">merge</span><span class="p">(</span><span class="n">hotels_bycountry</span><span class="p">,</span> <span class="n">on</span><span class="o">=</span><span class="s1">&#39;Country Code&#39;</span><span class="p">)</span>
<span class="n">airbnb_hotels_travel</span><span class="o">.</span><span class="n">rename</span><span class="p">(</span><span class="n">columns</span><span class="o">=</span><span class="p">{</span><span class="s1">&#39;Price&#39;</span><span class="p">:</span> <span class="s1">&#39;Airbnb Price&#39;</span><span class="p">,</span> <span class="s1">&#39;Count&#39;</span><span class="p">:</span> <span class="s1">&#39;# of Airbnb&#39;</span><span class="p">,</span>
                                     <span class="s1">&#39;price&#39;</span><span class="p">:</span> <span class="s1">&#39;Hotel Price&#39;</span><span class="p">,</span> <span class="s1">&#39;count&#39;</span><span class="p">:</span> <span class="s1">&#39;# of Hotels&#39;</span><span class="p">,</span> 
                                     <span class="s1">&#39;stars&#39;</span><span class="p">:</span> <span class="s1">&#39;Hotel Stars&#39;</span><span class="p">},</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[45]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">showinmap</span><span class="p">(</span><span class="n">dataset</span><span class="p">,</span> <span class="n">val</span><span class="o">=</span><span class="s1">&#39;Airbnb Price&#39;</span><span class="p">,</span> <span class="n">loc</span><span class="o">=</span><span class="s1">&#39;Country Code&#39;</span><span class="p">,</span> <span class="n">name</span><span class="o">=</span><span class="s1">&#39;Country Name&#39;</span><span class="p">,</span> <span class="n">filename</span><span class="o">=</span><span class="s1">&#39;Airbnb&#39;</span><span class="p">):</span>

    <span class="n">trace1</span> <span class="o">=</span> <span class="nb">dict</span><span class="p">(</span>
                  <span class="n">z</span><span class="o">=</span><span class="n">dataset</span><span class="p">[</span><span class="n">val</span><span class="p">],</span>
                  <span class="n">autocolorscale</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span> 
                  <span class="n">colorbar</span><span class="o">=</span><span class="p">{</span><span class="s2">&quot;title&quot;</span><span class="p">:</span> <span class="n">val</span><span class="p">},</span> 
                  <span class="n">colorscale</span><span class="o">=</span><span class="n">scale2</span><span class="p">,</span> 
                  <span class="n">locations</span><span class="o">=</span><span class="n">dataset</span><span class="p">[</span><span class="n">loc</span><span class="p">],</span>
                  <span class="n">marker</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">line</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">color</span><span class="o">=</span><span class="s2">&quot;rgb(180,180,180)&quot;</span><span class="p">,</span> 
                                        <span class="n">width</span><span class="o">=</span><span class="mf">0.5</span><span class="p">)),</span> 
                  <span class="n">reversescale</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span> 
                  <span class="n">text</span><span class="o">=</span><span class="n">dataset</span><span class="p">[</span><span class="n">name</span><span class="p">],</span>
                  <span class="nb">type</span><span class="o">=</span><span class="s2">&quot;choropleth&quot;</span><span class="p">,</span> 
                  <span class="n">zmin</span><span class="o">=</span><span class="mi">0</span>
    <span class="p">)</span>
    <span class="n">data</span> <span class="o">=</span> <span class="p">[</span><span class="n">trace1</span><span class="p">]</span>

    <span class="n">layout</span> <span class="o">=</span> <span class="nb">dict</span><span class="p">(</span>
                  <span class="n">geo</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">projection</span><span class="o">=</span><span class="p">{</span><span class="s2">&quot;type&quot;</span><span class="p">:</span> <span class="s2">&quot;Mercator&quot;</span><span class="p">},</span> 
                           <span class="n">showcoastlines</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> 
                           <span class="n">showframe</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span>
                           <span class="c1">#showland=True,</span>
                           <span class="c1">#landcolor=&#39;rgb(220,220,220)&#39;</span>
                  <span class="p">),</span> 
                  <span class="n">title</span><span class="o">=</span><span class="s2">&quot;World Map of &quot;</span> <span class="o">+</span> <span class="n">val</span>
    <span class="p">)</span>
    <span class="n">fig</span> <span class="o">=</span> <span class="nb">dict</span><span class="p">(</span><span class="n">data</span><span class="o">=</span><span class="n">data</span><span class="p">,</span> <span class="n">layout</span><span class="o">=</span><span class="n">layout</span><span class="p">)</span>
    <span class="k">return</span> <span class="n">py</span><span class="o">.</span><span class="n">iplot</span><span class="p">(</span><span class="n">fig</span><span class="p">,</span> <span class="n">validate</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span> <span class="n">filename</span><span class="o">=</span><span class="n">filename</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[46]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">showinmap</span><span class="p">(</span><span class="n">airbnb_hotels_travel</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stderr output_text">
<pre>/Users/Hope/anaconda3/lib/python3.7/site-packages/IPython/core/display.py:689: UserWarning:

Consider using IPython.display.IFrame instead

</pre>
</div>
</div>

<div class="output_area">

    <div class="prompt output_prompt">Out[46]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<iframe id="igraph" scrolling="no" style="border:none;" seamless="seamless" src="https://plot.ly/~ghuang920/42.embed" height="525px" width="100%"></iframe>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[47]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">showinmap</span><span class="p">(</span><span class="n">airbnb_hotels_travel</span><span class="p">,</span> <span class="n">val</span><span class="o">=</span><span class="s1">&#39;Hotel Price&#39;</span><span class="p">,</span> <span class="n">filename</span><span class="o">=</span><span class="s1">&#39;Hotels&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stderr output_text">
<pre>/Users/Hope/anaconda3/lib/python3.7/site-packages/IPython/core/display.py:689: UserWarning:

Consider using IPython.display.IFrame instead

</pre>
</div>
</div>

<div class="output_area">

    <div class="prompt output_prompt">Out[47]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<iframe id="igraph" scrolling="no" style="border:none;" seamless="seamless" src="https://plot.ly/~ghuang920/40.embed" height="525px" width="100%"></iframe>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[48]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">ax</span> <span class="o">=</span> <span class="n">sns</span><span class="o">.</span><span class="n">lmplot</span><span class="p">(</span><span class="n">data</span><span class="o">=</span><span class="n">airbnb_hotels_travel</span><span class="p">,</span> <span class="n">x</span><span class="o">=</span><span class="s1">&#39;TouristsInflow&#39;</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">&#39;Airbnb Price&#39;</span><span class="p">)</span>
<span class="n">pp</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stderr output_text">
<pre>/Users/Hope/anaconda3/lib/python3.7/site-packages/scipy/stats/stats.py:1713: FutureWarning:

Using a non-tuple sequence for multidimensional indexing is deprecated; use `arr[tuple(seq)]` instead of `arr[seq]`. In the future this will be interpreted as an array index, `arr[np.array(seq)]`, which will result either in an error or a different result.

</pre>
</div>
</div>

<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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92PGjBn44x//iDPPPBNbtmzBtGnT8NZbbyV8rqZpePfddwEAd911FwBg165dWLJkCT7++GN4PB4899xz2LBhA6ZNm4b//u//xg033IBLLrkE1157LW666SZUVlZi06ZNePPNN7vcge3vf/873nnnHfTr1w81NTX405/+hHnz5mH79u0IhUKYNWsWXn/99fjj77zzTlx++eWYNm0aDh48iKlTp2LAgAG47LLL8OGHH2LSpEn46KOPEAgEUF9fj6uuugqrVq3CnDlzktSi1BNr167FV199hZ/+9KcA7J+p008/vcOmOEOGDMHzzz+Pe++9F4sWLerV+zBwKSP885//xEknnRQfXhg8eDCGDh16VBuQnH322YfdN2DAAJx88smoqqrCqFGjMGrUKPzoRz867HFjx45FTU0N3n//fZx33nmYMWNGl+9x5plnxvchrqiowAcffNBtPcFgEP/617/w0ksvAQCKioowceJEfPjhh7jrrruwYMECGIaBjz76CNOnT0d9fT3OP/98HDx4EBUVFQm/X0o+wzAwduzY+JBXa2srDMPoclOc3/zmN71+H140o4zQefu92H26rgMA2q9AV1W1w+O62gNWlmW88sormDt3LoqKijBnzhw8+eSThz1u6tSpWLZsGUaMGIEPP/wQEyZMOOz1AcDr9ca/FgQBR1oRb5pml/fpuo7S0lKceuqpWL16NTRNw8SJE/Hpp5/i/fffx+jRo7t9TUqt4cOH47333sO+fftgWRZ+/etf44UXXsCJJ56IPXv2YNu2bQCA//mf/zmmaw4MXMoIZ511FrZu3Yp//etfAIAtW7bgH//4B4YPH47S0lJs3boVqqpCVVX89a9/Tfh6GzduxIQJE3Dqqadi+vTpmDZtWvy1ZVmGpmkAgKuuugpbt27F5MmT8fDDD6OpqQn79+8/pu+lqKgIp59+OpYsWQIAOHjwIJYtW4bzzjsPAHDZZZfhiSeewIgRI1BYWIjjjz8eixcvxpgxY47pfan3TjvtNPzyl7/Ev//7v+OKK66AaZq4+eabUVxcHN8UZ/z48fjLX/5yTJvicEiBMkJZWRmeeuop/PrXv4aqqhBFEY899hhOOOEE9O/fHytWrEBlZSXKy8txzjnnxHsc3amoqMCll16Kqqoq5OXlwefzYfbs2QDs2RGPP/44VFXFvffei3nz5uGJJ56AIAiYMWMG+vfvn/D1E3nyySfjMxc0TcOECRNw5ZVXArADd+7cubjvvvsAACNHjkRtba2rT6/IVKtWrYp//ZOf/AQ/+clPDnvMhRdeiAsvvDAp78fdwoiIHMIhBSIihzBwiYgcwsAlInIIA5eIyCEMXCIihzBwiYgcwsAlInIIA5eIyCH/D06ibUOkbHzLAAAAAElFTkSuQmCC
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[49]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">sns</span><span class="o">.</span><span class="n">lmplot</span><span class="p">(</span><span class="s1">&#39;Hotel Price&#39;</span><span class="p">,</span> <span class="s1">&#39;Airbnb Price&#39;</span><span class="p">,</span> <span class="n">airbnb_hotels_travel</span><span class="p">)</span>
<span class="n">pp</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[50]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">airbnb_hotels_travel</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[50]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country Name</th>
      <th>Country Code</th>
      <th>Region</th>
      <th>IncomeGroup</th>
      <th>TouristsInflow</th>
      <th>Airbnb Price</th>
      <th># of Airbnb</th>
      <th>Hotel Stars</th>
      <th>Hotel Price</th>
      <th># of Hotels</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Australia</td>
      <td>AUS</td>
      <td>East Asia &amp; Pacific</td>
      <td>High income</td>
      <td>7450000.0</td>
      <td>165.077177</td>
      <td>40219</td>
      <td>3.665661</td>
      <td>193.910612</td>
      <td>4956</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Austria</td>
      <td>AUT</td>
      <td>Europe &amp; Central Asia</td>
      <td>High income</td>
      <td>26728000.0</td>
      <td>67.076562</td>
      <td>7889</td>
      <td>3.013974</td>
      <td>114.366708</td>
      <td>5748</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Belgium</td>
      <td>BEL</td>
      <td>Europe &amp; Central Asia</td>
      <td>High income</td>
      <td>8355000.0</td>
      <td>68.052057</td>
      <td>7415</td>
      <td>2.803471</td>
      <td>115.643554</td>
      <td>1591</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Canada</td>
      <td>CAN</td>
      <td>North America</td>
      <td>High income</td>
      <td>17971000.0</td>
      <td>107.010622</td>
      <td>30692</td>
      <td>2.752049</td>
      <td>129.664729</td>
      <td>3925</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Germany</td>
      <td>DEU</td>
      <td>Europe &amp; Central Asia</td>
      <td>High income</td>
      <td>34970000.0</td>
      <td>57.222044</td>
      <td>20568</td>
      <td>3.007837</td>
      <td>99.543638</td>
      <td>13391</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Spain</td>
      <td>ESP</td>
      <td>Europe &amp; Central Asia</td>
      <td>High income</td>
      <td>68175000.0</td>
      <td>97.136425</td>
      <td>45732</td>
      <td>2.666833</td>
      <td>88.612824</td>
      <td>12803</td>
    </tr>
    <tr>
      <th>6</th>
      <td>France</td>
      <td>FRA</td>
      <td>Europe &amp; Central Asia</td>
      <td>High income</td>
      <td>84452000.0</td>
      <td>94.431201</td>
      <td>56505</td>
      <td>2.478227</td>
      <td>104.951777</td>
      <td>12111</td>
    </tr>
    <tr>
      <th>7</th>
      <td>United Kingdom</td>
      <td>GBR</td>
      <td>Europe &amp; Central Asia</td>
      <td>High income</td>
      <td>34436000.0</td>
      <td>93.020880</td>
      <td>60966</td>
      <td>3.204871</td>
      <td>116.529650</td>
      <td>14794</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Greece</td>
      <td>GRC</td>
      <td>Europe &amp; Central Asia</td>
      <td>High income</td>
      <td>23599000.0</td>
      <td>52.935767</td>
      <td>5122</td>
      <td>2.606760</td>
      <td>85.375987</td>
      <td>7286</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Ireland</td>
      <td>IRL</td>
      <td>Europe &amp; Central Asia</td>
      <td>High income</td>
      <td>9528000.0</td>
      <td>103.780488</td>
      <td>6724</td>
      <td>3.268726</td>
      <td>104.791336</td>
      <td>1206</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Italy</td>
      <td>ITA</td>
      <td>Europe &amp; Central Asia</td>
      <td>High income</td>
      <td>50732000.0</td>
      <td>93.964180</td>
      <td>33110</td>
      <td>2.973318</td>
      <td>113.031926</td>
      <td>19884</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Netherlands</td>
      <td>NLD</td>
      <td>Europe &amp; Central Asia</td>
      <td>High income</td>
      <td>15007000.0</td>
      <td>133.993607</td>
      <td>15173</td>
      <td>3.087690</td>
      <td>109.557754</td>
      <td>2198</td>
    </tr>
    <tr>
      <th>12</th>
      <td>United States</td>
      <td>USA</td>
      <td>North America</td>
      <td>High income</td>
      <td>77774000.0</td>
      <td>156.051199</td>
      <td>132581</td>
      <td>2.446422</td>
      <td>106.612129</td>
      <td>38195</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[51]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">airbnb_hotels_travel</span><span class="o">.</span><span class="n">plot</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">x</span><span class="o">=</span><span class="s1">&#39;Country Name&#39;</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="p">[</span><span class="s1">&#39;Airbnb Price&#39;</span><span class="p">,</span> <span class="s1">&#39;Hotel Price&#39;</span><span class="p">])</span>
<span class="n">pp</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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oLvvvltdunRRbGyst8sqkeHDh2vPnj2KiIhwLrNYLPrHP/7hxarcM3HiRE2YMEEffPCBBg4cqM8++0zZ2dneLsstCxYs0PHjx7Vy5Ur169dP1apVU0xMjB5//HGVK1fO2+W57C9/+YvCwsJ0++23FwkD/mr8+PG68cYb9eOPPyowMFBHjhxRXFycEhMTvV2aSypUqOC3H1x+jxn2zb59+yRJ48aN0wMPPKD27dvLYrFow4YN+vzzz71cnfvWrVunDRs2aPr06Tp9+rQ6duyo9u3b++VBgTlz5ighIUFr167Vfffdp7Fjx6pnz55+GZozMzP1zDPPaMKECYqJiVHHjh19MgNcE6E5IiJC5cqVU506dbR//361bdtW58+f93ZZbgkNDVVeXp5uueUW7dmzRw0bNvR2SSW2d+9erV27VoGBgd4upcTCwsLUqFEjffPNNzp//rxGjhypNm3aeLsst1WvXl0dO3aU1WrVxx9/rAULFmjGjBl66aWX1LJlS2+X55JTp07pgw8+8HYZHrNnzx4tX75c//73vxUaGqrJkycrOjra22W5LCYmRjNmzFCjRo1ktf7vT5I/nmm6zCz7Rro0TOv11193Po6KitI777zjxYpKJjQ0VB07dlTHjh21adMmvfHGG5ozZ44aN26sUaNGqVatWt4u0SV169bV7Nmz1b59e11//fXKz8/3dklusdvt2r17tz777DMtXLhQe/fuVWFhobfLusI1EZorV66suXPnqnHjxpo6daqkS6fP/FH79u01cOBAJSYm6qmnntLnn3+uypUre7usEqlXr54OHz6s2rVre7uUEgsJCdGhQ4dUp04dbd++XY0aNfLbX2JLlizRypUrlZ6ero4dO+rDDz9UlSpVlJaWppiYGL8LzXfddZf27dununXrersUj7BYLMrLy3MeNT979qxfHkHftWuXvvnmG33zzTfOZf56pukys+wb6VLIXLZsmVq3bi273a6VK1fqhhtu8HZZbjt8+LBWrVqlNWvWqFq1anrppZcUGRmpL7/8Us8995w2btzo7RKL7aabbtKECRO0e/duTZ06VZMmTVK1atW8XZZbRo4cqSlTpqhfv36qUaOGunTpoldeecXbZV3B4vj14D6TysrK0tatW9W2bVstWLBAycnJ6t27txo1auTt0txyebD/L7/8oh9++EFNmjRRaGiot8ty24oVKxQXF6eIiAgFBgbK4XDIYrHon//8p7dLc9n27duVlJSkqVOnqlu3bjpy5IhiY2M1evRob5fmspdfflmxsbF6+OGHr3huw4YNioqK8kJV7ouJidG+ffsUHh6u4OBgv/4+ky793CxZskSHDx9W69attWnTJg0ePNjvrtWIjo7W6tWrvV2GR5ll30jS8ePHNWHCBH311VeyWCx69NFHFR8f77cHa1q0aKFOnTopJiZG1atXL/Lcm2++qbi4OC9V5rqsrCx99tlnql+/vmrVqqWkpCR17NhR119/vbdLc8uFCxd09OhR3XnnncrOztZ1113n7ZKuYOrQnJ6eLpvNptTU1Ks+70+fyBYtWqSnnnpKc+bMuerz/jwmsHXr1ho/fvwV++O3v9D8UWZmpl8flTlw4IAyMzOLXDjnr6fNjx8/ftXl/vx99tNPP+mrr75SYWGhHn74Yb+8mG748OHq37+/ac4AXGaGfQPftGLFij98vmPHjmVUied88cUXGjt2rAoLC7Vo0SJFR0crMTFRTZo08XZpRZh6eEZ8fLzmzp2rHj16yGKxFPnD729HmEz82UaVKlVSw4YN/fb0pST17NnzD+v3x1PN48eP1+bNm1WjRg3nMn88bb5lyxY1b978d6/299fQvH//fr377ruaMWOGfv75Z40dO1YTJkzwu2FOBw8eVExMjGw2m8qVK+f3ZwAk8+wbSfr88881c+bMKz48+9v++e1sIL/NA3v37vVGWW756quvJElHjhzR4cOH1axZMwUGBmrbtm267bbb/DI0T58+XR9++KGee+452Ww2LVy4UMOHDyc0l6W5c+dKujQNmL/r2rWrpEtHy8w2f+ktt9yiLl266JFHHikyK4M/HT0fMmSIJGnx4sUKCQlxXjy3Zs0a5ebmerk692zbtk3r16/3yzmmf+2HH35Q8+bNnX9ofssf/8BI0quvvur8GalTp46ef/55jRkzRh999JGXK3PNW2+95e0SPM4s+0aS3njjDY0ePdrvZ525PBuIGVzOAD179tSqVat04403Srp0ZvOFF17wZmlus9vtRWYwue2227xYze8zdWg2GkTuj+Hzv//9ry5cuOC3Y5auplq1an41VOZqHnroIUnS5MmTtWzZMufy+++/3y+n/5GkGjVqmOIMx4svvijp6j/vOTk5ZV2Ox2RnZ6tp06bOx48++qjz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uXPVokWLq55e9rexmZK0cOFCbd68WYmJiXrqqadUq1Yt2e12vf/++94uzWVpaWn69NNP1a9fP02aNEnJyckaMGCA34437dSpk4YMGeI8Ortp0yZ98MEHfjvkxCyzGjz33HOKj49XrVq1JF26gdPYsWM1b948L1fmviNHjmjUqFH64YcfFBISolq1amnq1Kl+eUfAdevWafHixZo9e7aefPJJBQQEqG7dun531ikrK0sZGRlKSEhQfHy8c7nValV4eLhfDgk00wxHHTt21IoVKzRr1iw9+OCDeuihhxQdHa21a9d6u7QironQHBsbq3/84x+muCFIhw4d9Mknnyg2Nlavv/667rjjDsXGxvrcN1ZxXB5mcvz48as+76+3N87KylL58uX1yy+/6IcfflCTJk0UGhrq7bKueTExMVf8kbn8ixre07ZtW3366afOxw6HQ23atPHrKecuu3jxoux2u8qXL+/tUkrk8q3NL168qJSUFN11111+PY7eTMwyne5TTz2luXPn6vPPP9fx48c1cOBARUVFacOGDd4urQj/+2jlhoCAANPcEKRjx45q0qSJHnjgAdWrV09t2rTRU0895e2y3BIRESGp6NjGy0JCQnThwgXdcccdZV1WiZw7d06rV69WRkaGc6zZ/v37/fJCk/nz5+vtt9++YnaWvXv3eqmiknnkkUf09ttvq0uXLgoMDNTatWtVp04dpaamSpJP3n3qj5hlVoN77rlHo0aNUuvWreVwOLR69Wq/HtYkXTpaHh8fr+PHjyspKUnPP/+83nzzTd18883eLq3YzHZH3avdD0D63wcCf/y9ZqYZjvr06aNhw4Y5z2isXr1a9957r7fLusI1caTZbDcEsdvtzhsBnDlzxnnfeX81ZMgQ/fjjj3riiSckSf/6178UERGhixcvKjo6Wn369PFugS7o27evwsLCrpjRwB9Dc4sWLbRw4UK/C5O/5/KFZpf3y69/9VksFr8bDtSmTZsrxgCGh4crLi7O26W5JC8vTwsXLnT+nn7kkUf09NNP++Xp8sueeeYZ9e3bV4mJiVq+fLmWLFmilStX+tXUk7936v8yfxwCYDYtWrTQqlWrrpjh6L333vN2aS7LzMxUhQoVipzRCAsLKzKdni/w399KLjDTDUF69ux51U/L/njU/LL09HQtX75cFSpUkHQpRA8cOFCLFi1Sp06d/Co0nzp1Sh988IG3y/CI2rVr66abbvJ2GR6xZcsWzZ8/XzVr1tSmTZu0dOlS3X333Xr++edVrlw5b5fnFrPManDq1Cm1atVKrVq1knTpA8y5c+f8+mDA2bNn1aRJEyUmJspisahLly5+FZiloqH42LFj+umnn9SkSROdOHHC54LMtcoMMxydOHFCDodD/fv319/+9jfnwYywsDA999xzWr9+vZcrLMrUodmMNwQZMmSI8/8FBQX65z//6Qyb/urs2bNFxpsHBwcrMzNTVqvV78bN3XXXXdq3b5/q1q3r7VJKrFevXoqOjla9evWK3KHN307Lzps3T2vXrtXkyZO1b98+jRw5UmPGjNHevXs1depUvzsye5lZZjV44YUXdODAAd1xxx3OedptNpsCAwM1YcIEvxyfGRISol9++cX5+2vHjh1FZjfwJ2vXrtU777yjnJwcffzxx+ratatefvlldejQwdulXfPMMMPRrFmz9NVXX+nkyZPq3r27c7nVavXJ+dpNPTzj2LFjzhuC/Ppq2cs3BPH325te9uSTT/rlGKbLpk2bpl27dql169ay2+3auHGjGjRooFtuuUVr1qzR//3f/3m7xGKLiYnRvn37FB4eruDgYOd4OX879S9duui0ZcuWV1yQ6W+nZdu3b69FixYpNDRUiYmJSk1N1fTp0/3+grP169dr0aJFfj+rwcCBAzV48GDn+MX9+/drzpw5iouL0+DBg/1yZqAffvhB8fHxOnLkiGrWrKnMzEz99a9/9ctbNsfExGjBggXq0aOHVqxYoZMnT6pv375FLt6Ed5hphqP33ntP/fv393YZhkx9pNmMNwS5fNGS9L+752VkZHixopIbMWKEtmzZov/85z8KDAzUs88+q2bNmunbb7/1uwBweSpAMwgKCvLLsdi/ZbFYnLOXfPXVV3r66aedy/1ZSEiI3n//fVksFi1btkwpKSl+eYbj+PHjRS74ufPOO3XkyBFVrVpVdrvdi5W57/Tp01q6dKlSUlJUWFio2rVr++2R5oCAgCKzf0RERDivqYF3Va5cWf369ZMkjR492svVuG///v3OgzHff///2rvXqKjOsw3A9zBIWWgUjSBKp6glhhhrJDEaTrGSRhRUGA2GaoIlrlCCQoOxKbGAyEGiIFSWFWk8RAWjJHI0rgAGqaIEu5ZW6hmMKcYuT5CgDOoAw/eD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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[52]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">ax</span> <span class="o">=</span> <span class="n">sns</span><span class="o">.</span><span class="n">lmplot</span><span class="p">(</span><span class="n">data</span><span class="o">=</span><span class="n">airbnb_hotels_travel</span><span class="p">,</span> <span class="n">x</span><span class="o">=</span><span class="s1">&#39;Airbnb Price&#39;</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">&#39;Hotel Price&#39;</span><span class="p">)</span>
<span class="n">pp</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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o0djMplYtGgRW7ZsiXap3QSDQVRVpb29nUAgQCAQwGQy4fF4KCwsBKCkpCQm6t6wYQOrV68mJycHgN27d5/x8z1+/HjM1H9qzRaLhdWrV5OamoqiKEyYMIETJ07EVM1nqhvA5/OxatUq7rrrrvAxv9/Pp59+yrx584DY+qy3bdtGYWEhkyZNAmDlypVcccUVMfdZd0iY1cL0cOTIEcxmM7fffjtVVVV8+9vf5sILL8Rut4efk5OTQ01NTRSrPF1qaip33303V155JUlJScycOROz2dytbrvdHhN1r1mzptvj2traM36+px6PZv2n1jxy5EhGjhwJQGNjI+vXr2ft2rUxVTOcXjfAk08+yXXXXceoUaPCx5qamkhNTcVkCsVFLH3WR44cITk5mXvvvZeDBw9y8cUXs2zZMvbs2RNTn3UHucLth2AwSFlZGb/5zW949dVX2b17N8eOHUNROpeD0zSt2+NYsHfvXv7617/ywQcf8PHHH2MwGNi2bVvM1w2gquoZ6+zpeCypqanhJz/5Cddddx2zZ8+O+Zq3bdtGVVUV1113XbfjZ6ozVuoOBoNs3bqV++67j9dff5329nZeeOGFmP2sJXD7ITs7m6KiIrKysrDZbHzve9+jtLSUurq68HPq6uq6fUWLBVu3bqWoqIjhw4djsVgoKSlh+/bt3equr6+PuboBHA7HGT/fU4/HWv0HDhzghhtu4Ac/+AF33HEHcPrPEms1b968mf3793PNNdewcuVKysvLueeee8jKyqKtrY1gMAjE1p/x7Oxspk2bxujRozEajVx55ZXs3r07Zj9rCdx++M53vsPWrVtpbW0lGAzy8ccfM3/+fA4dOsSRI0cIBoNs3ryZuXPnRrvUbiZNmkRpaSlutxtN03j//feZNWsWVquVnTt3AqFRDLFWN8C0adPO+PmOHDkyZut3Op3ceuut3H333dxyyy3h47FcM8DatWt555132LRpE48++igFBQX87ne/w2w2M2PGDN5++20ANm7cGDN1X3rppVRUVFBVVQXABx98QH5+fsx+1tLD7Ydp06Zx2223ceONN+L3+7nkkktYvHgxF1xwAXfeeSder5fLL7+c+fPnR7vUbi699FL27NlDSUkJZrOZqVOn8rOf/YwrrriClStX4nQ6yc/PZ8mSJdEu9TRWq5XHHnvsjJ/vunXrYrL+1157jfr6el588UVefPFFAL773e9y9913x2zNvVm9ejXLli3jD3/4A3l5eTz11FPRLgmAvLw8Hn74YW6//Xa8Xi+TJ0/mgQceAGLzz4fs+CCEEDqRloIQQuhEAlcIIXQigSuEEDqRwBVCCJ1I4AohhE4kcEXM8Pv9XHrppdx2223hY19++WW3ef1dLVu2jD/+8Y/9Osfrr7/Oz3/+816ft337di666CKuueYarr32Wq655hpKSkp4//33z/j8V155hRdeeKFftYihR8bhipjx3nvvMWnSJMrLyzlw4ADjxo1j6tSpPPPMM1GpZ8yYMWzatCn8eO/evSxevJh//vOfZGVldXvu4sWL9S5PxCEJXBEzXnnlFa666irGjBnDn//8Zx5++GG2b9/OI488wubNm1m2bBnNzc0cO3aMb3/72wDs3LmTd999F6fTySWXXMIDDzyAyWQKT+7Ytm0btbW14QkrEJqaeuutt1JbW8vIkSN55JFHui100pNJkyZhs9k4fvw469ev54svvqC2tpaJEycyduxYmpqaWLVqFYcOHWLVqlU0NjZiMBj4xS9+wVVXXUVNTQ0PP/wwVVVV+P1+FixYwO233x7Jj1TEGGkpiJjw9ddf8/nnnzN//nyuvfZaNm3aRFNT02nP83g8vPXWWyxduhSA6upq/vSnP7Fx40b27t3Lhg0bgNAyg5mZmfzlL3/hmWeeYe3atXi9XoBwIL755ptMmDDhjKtmncnf//53DAYD48ePB+D48eO88cYbrFu3rtvz7rvvPubPn89bb73FCy+8wFNPPYXT6WTp0qVcd911vP7667z22muUlpaGp8uKoUGucEVMeOWVV/jOd75DZmYmmZmZjBo1ig0bNoTXM+0wffr0bo+vueYakpOTAbj66qv56KOPwley//Ef/wFAfn4+Pp8Pt9sNQHFxMWPHjgXg+uuv5/rrrz9jTUePHuWaa64BIBAI4HA4eO6550hKSgKgsLAwvGRhh+bmZvbu3csPf/hDIDT19B//+Adut5tPP/2UlpYWfv/73wPgdrvZu3cvV1111QA+MRGPJHBF1LndbjZt2oTFYuG73/0uEFoA5uWXX6agoKDbczvCtYPRaAz/WtO0bgFotVqBzqUEO2axd32NqqqnhWaHU3u4pzq1FiD8Xl2XAjx48CB2ux1N0/jLX/4SDuzGxsZwjWJokJaCiLo333yTYcOG8fHHH/P+++/z/vvvh68KGxsbz/rat956C5/Ph9fr5Y033ujTilDbt2/nxIkTAPzlL38Z1FWkUlNTyc/PZ+PGjQBUVVWxePHi8O4DHYvZtLa2hm/AiaFDrnBF1L3yyiv853/+Z7crz/T0dG6++Wb+9Kc/nfW1o0aN4sYbb8TlcnHFFVfwgx/8oNfzTZgwgeXLl1NfX88FF1zAww8/fK4/QjdPPvkkDz30EC+99BKKorBmzRrsdjvr1q3jkUceYdGiRfh8PhYuXMjVV189qOcWsU1WCxNCCJ1IS0EIIXQigSuEEDqRwBVCCJ1I4AohhE4kcIUQQicSuEIIoRMJXCGE0IkErhBC6OT/A4i5L3VO4jI0AAAAAElFTkSuQmCC
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[53]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">airbnb_hotels_travel</span><span class="o">.</span><span class="n">plot</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">x</span><span class="o">=</span><span class="s1">&#39;Country Name&#39;</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="p">[</span><span class="s1">&#39;# of Airbnb&#39;</span><span class="p">,</span> <span class="s1">&#39;# of Hotels&#39;</span><span class="p">])</span>
<span class="n">pp</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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e/fu+uqrrxQbG6tjx455uyyPBQYGqrKyUj/72c+0fft2hYeHe7ukRtmxY4fy8vLk6+vr7VIaLTg4WAMGDNAnn3yiY8eOKTExUXfeeae3y2qUzp07a9iwYbLb7Xr99deVmZmpOXPm6Omnn9Ydd9zh7fIarKSkRC+99JK3y2gy27dv11tvvaX169crMDBQ06dPV1xcnLfL8kh8fLzmzJmjAQMGyG7/v19vrfFdMMlaz410einapEmTam9HRUVp/vz5XqzIc4GBgRo2bJiGDRumd955R88//7xeeOEFDRw4UM8++6yuvPJKb5fotl69eulvf/ubhgwZoksvvVRVVVXeLsltNTU1+uKLL/Tuu+/q1Vdf1Y4dO1RdXe3tss6LAO6GDh06aOHChRo4cKBmzpwp6fRbhK3VkCFD9OijjyojI0O//e1v9f7776tDhw7eLstj1157rfbt26du3bp5u5RGa9Omjfbs2aPu3btr06ZNGjBgQKv8YXjGG2+8oZycHBUXF2vYsGFasmSJwsLCVFhYqPj4+FYVwK+++mrt3LlTvXr18nYpTcJms6mysrL2aP7hw4db7ZH9f//73/rkk0/0ySef1I611nfBJGs9N9Lp0Lp8+XLFxMSopqZGOTk5uvzyy71dlkf27dun3NxcrVy5Up06ddLTTz+tQYMG6aOPPtLvf/97vf32294u0S0/+clPNGXKFH3xxReaOXOmpk2bpk6dOnm7LLclJiZqxowZeuihh9SlSxf95je/0XPPPeftss7L5jp7ESN+VHl5udatW6fY2FhlZmZq48aNuv/++zVgwABvl+axMydaHDx4UJ9//rluueUWBQYGerssj2RnZys5OVmhoaHy9fWVy+WSzWbT//zP/3i7NLdt2rRJixcv1syZM3Xvvffq22+/1V133aWkpCRvl+aRZ555RnfddZf69+9f777Vq1crKirKC1V5Jj4+Xjt37lT79u0VEBDQqv+dSaf/37zxxhvat2+fYmJi9M4772js2LGt8tyWuLg4rVixwttlNBkrPTeSdODAAU2ZMkUff/yxbDabbr75Zk2cOLFVHvi5/fbblZCQoPj4eHXu3LnOfX/5y1+UnJzspco8U15ernfffVfXXXedrrzySi1evFjDhg3TpZde6u3S3FZRUaH9+/erZ8+eOnHihC655BJvl3ReBPAGKC4ulsPhUEFBwXnvb22vEpcuXarf/va3euGFF857f2tdQxkTE6PJkyfXez7O/eHYGh09erTVHik64+uvv9bRo0frnLjYGpcGHDhw4Lzjrfnf2TfffKOPP/5Y1dXV6t+/f6s9iXHChAkaPXq0Zd6dkKzz3KBlys7O/tH7hw0bZqiSpvHhhx8qNTVV1dXVWrp0qeLi4pSRkaFbbrnF26XVwxKUBpg4caIWLlyo++67TzabrU6AaI1Hvqz6mqtt27YKDw9v1W/Rjhw58kfrb61vpU+ePFlr1qxRly5dasda29KA9957T7fddtsPXrGhtQbwr776SgsWLNCcOXO0a9cupaamasqUKa1yKdfu3bsVHx8vh8MhPz+/Vv/uhJWeG0l6//33NXfu3HovxFvT83PuFV3OzQM7duzwRlke+/jjjyVJ3377rfbt26fIyEj5+vpqw4YNuuqqq1pdAJ89e7aWLFmi3//+93I4HHr11Vc1YcIEAnhrtXDhQkmnLw1nBb/73e8knT6SZ6Xr4/7sZz/Tb37zG9100011rqzRmo7oP/7445KkrKwstWnTpvakxZUrV+rUqVNers5zGzZsUH5+fqu9jrkkff7557rttttqf2Gdq7X9ojrjT3/6U+3/ke7du+uPf/yjUlJS9Nprr3m5Mve9+OKL3i6hSVnpuZGk559/XklJSa36CkJnruhiFWcywMiRI5Wbm6t27dpJOv2u62OPPebN0jxSU1NT50o0V111lRer+XEE8Aa40AL+1hpi//Of/6iioqJVrvE6n06dOrW65UDnuvHGGyVJ06dP1/Lly2vH+/bt2+ouB3W2Ll26tPp3Xp544glJ5///fvLkSdPlNJkTJ04oIiKi9vbNN99ce5J5a9OpUye99tpr+uijj+R0OjVgwADdd9993i7LY1Z6bqTT71Ledttt3i6jSZSWlio3N1cVFRV1PshuxowZ3i7NI0VFRQoJCam9HRgYqOLiYi9W5JmwsDC99957stlsKisr0+LFi1tsLiCAN8CZUGQ1NptNt912m7p27aqAgIDa8da0LOBsrelI94WcOnVKe/bsUdeuXSWdfiva6XR6uSrPXX755YqNjdV1111X50NEWuOL1zVr1mju3Ll1PkH25MmT+vDDD71dmkfatWun1157TUOGDJEk5eXlqX379l6uyjMzZszQvn37dNddd8nlcunNN9/U/v37lZKS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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[54]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">ax</span> <span class="o">=</span> <span class="n">sns</span><span class="o">.</span><span class="n">lmplot</span><span class="p">(</span><span class="n">data</span><span class="o">=</span><span class="n">airbnb_hotels_travel</span><span class="p">,</span> <span class="n">x</span><span class="o">=</span><span class="s1">&#39;# of Hotels&#39;</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">&#39;# of Airbnb&#39;</span><span class="p">)</span>
<span class="n">pp</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Daily-Price----Weekly-Price----Montly-Price?">Daily Price -- Weekly Price -- Montly Price?<a class="anchor-link" href="#Daily-Price----Weekly-Price----Montly-Price?">&#182;</a></h3>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[55]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">airbnb_p</span> <span class="o">=</span> <span class="n">airbnb</span><span class="o">.</span><span class="n">loc</span><span class="p">[:,</span> <span class="p">[</span><span class="s1">&#39;City&#39;</span><span class="p">,</span> <span class="s1">&#39;State&#39;</span><span class="p">,</span> <span class="s1">&#39;Country Code&#39;</span><span class="p">,</span> <span class="s1">&#39;Country&#39;</span><span class="p">,</span> <span class="s1">&#39;Latitude&#39;</span><span class="p">,</span> <span class="s1">&#39;Longitude&#39;</span><span class="p">,</span> 
                        <span class="s1">&#39;Property Type&#39;</span><span class="p">,</span> <span class="s1">&#39;Room Type&#39;</span><span class="p">,</span> <span class="s1">&#39;Bathrooms&#39;</span><span class="p">,</span> <span class="s1">&#39;Bedrooms&#39;</span><span class="p">,</span> <span class="s1">&#39;Beds&#39;</span><span class="p">,</span>
                        <span class="s1">&#39;Price&#39;</span><span class="p">,</span> <span class="s1">&#39;Weekly Price&#39;</span><span class="p">,</span> <span class="s1">&#39;Monthly Price&#39;</span><span class="p">,</span>
                        <span class="s1">&#39;Availability 30&#39;</span><span class="p">,</span> <span class="s1">&#39;Availability 60&#39;</span><span class="p">,</span> <span class="s1">&#39;Availability 90&#39;</span><span class="p">,</span> <span class="s1">&#39;Availability 365&#39;</span><span class="p">]]</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[56]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">airbnb_pricing</span> <span class="o">=</span> <span class="n">airbnb_p</span><span class="o">.</span><span class="n">dropna</span><span class="p">()</span>
<span class="n">airbnb_pricing_plot</span> <span class="o">=</span> <span class="n">airbnb_pricing</span><span class="o">.</span><span class="n">groupby</span><span class="p">([</span><span class="s1">&#39;Country&#39;</span><span class="p">,</span><span class="s1">&#39;Country Code&#39;</span><span class="p">])</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">countries</span><span class="p">,:]</span><span class="o">.</span><span class="n">reset_index</span><span class="p">()</span>
<span class="n">airbnb_pricing_plot</span><span class="p">[</span><span class="s1">&#39;Weekly Price (Ratio)&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">airbnb_pricing_plot</span><span class="p">[</span><span class="s1">&#39;Weekly Price&#39;</span><span class="p">]</span><span class="o">/</span><span class="n">airbnb_pricing_plot</span><span class="p">[</span><span class="s1">&#39;Price&#39;</span><span class="p">]</span>
<span class="n">airbnb_pricing_plot</span><span class="p">[</span><span class="s1">&#39;Monthly Price (Ratio)&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">airbnb_pricing_plot</span><span class="p">[</span><span class="s1">&#39;Monthly Price&#39;</span><span class="p">]</span><span class="o">/</span><span class="n">airbnb_pricing_plot</span><span class="p">[</span><span class="s1">&#39;Price&#39;</span><span class="p">]</span>
<span class="n">airbnb_pricing_plot</span><span class="p">[</span><span class="s1">&#39;Next Month&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">airbnb_pricing_plot</span><span class="p">[</span><span class="s1">&#39;Availability 60&#39;</span><span class="p">]</span> <span class="o">-</span> <span class="n">airbnb_pricing_plot</span><span class="p">[</span><span class="s1">&#39;Availability 30&#39;</span><span class="p">]</span>
<span class="n">airbnb_pricing_plot</span><span class="p">[</span><span class="s1">&#39;Next 2nd Month&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">airbnb_pricing_plot</span><span class="p">[</span><span class="s1">&#39;Availability 90&#39;</span><span class="p">]</span> <span class="o">-</span> <span class="n">airbnb_pricing_plot</span><span class="p">[</span><span class="s1">&#39;Availability 60&#39;</span><span class="p">]</span>
<span class="n">airbnb_pricing_plot</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[56]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>Country Code</th>
      <th>Latitude</th>
      <th>Longitude</th>
      <th>Bathrooms</th>
      <th>Bedrooms</th>
      <th>Beds</th>
      <th>Price</th>
      <th>Weekly Price</th>
      <th>Monthly Price</th>
      <th>Availability 30</th>
      <th>Availability 60</th>
      <th>Availability 90</th>
      <th>Availability 365</th>
      <th>Weekly Price (Ratio)</th>
      <th>Monthly Price (Ratio)</th>
      <th>Next Month</th>
      <th>Next 2nd Month</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Australia</td>
      <td>AUS</td>
      <td>-35.255923</td>
      <td>148.579503</td>
      <td>1.143305</td>
      <td>1.123466</td>
      <td>1.413991</td>
      <td>101.317672</td>
      <td>581.282955</td>
      <td>2133.324197</td>
      <td>10.245106</td>
      <td>25.514226</td>
      <td>42.836857</td>
      <td>190.611851</td>
      <td>5.737232</td>
      <td>21.055796</td>
      <td>15.269120</td>
      <td>17.322631</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Austria</td>
      <td>AUT</td>
      <td>48.206145</td>
      <td>16.360578</td>
      <td>1.088804</td>
      <td>1.134818</td>
      <td>1.918523</td>
      <td>63.599648</td>
      <td>403.174678</td>
      <td>1271.645955</td>
      <td>7.908558</td>
      <td>19.807151</td>
      <td>34.848769</td>
      <td>208.286049</td>
      <td>6.339260</td>
      <td>19.994544</td>
      <td>11.898593</td>
      <td>15.041618</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Belgium</td>
      <td>BEL</td>
      <td>50.886356</td>
      <td>4.370318</td>
      <td>1.109216</td>
      <td>1.144823</td>
      <td>1.693597</td>
      <td>63.074806</td>
      <td>382.639138</td>
      <td>1231.938959</td>
      <td>8.691801</td>
      <td>21.588270</td>
      <td>37.825254</td>
      <td>206.408139</td>
      <td>6.066434</td>
      <td>19.531395</td>
      <td>12.896469</td>
      <td>16.236984</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Canada</td>
      <td>CAN</td>
      <td>45.508554</td>
      <td>-80.998197</td>
      <td>1.118675</td>
      <td>1.187618</td>
      <td>1.525156</td>
      <td>79.814412</td>
      <td>475.785124</td>
      <td>1541.904596</td>
      <td>10.295346</td>
      <td>23.224010</td>
      <td>37.400464</td>
      <td>202.018269</td>
      <td>5.961143</td>
      <td>19.318624</td>
      <td>12.928665</td>
      <td>14.176454</td>
    </tr>
    <tr>
      <th>4</th>
      <td>France</td>
      <td>FRA</td>
      <td>48.864023</td>
      <td>2.348225</td>
      <td>1.037783</td>
      <td>0.935244</td>
      <td>1.546196</td>
      <td>78.952682</td>
      <td>506.252702</td>
      <td>1649.709362</td>
      <td>7.400979</td>
      <td>17.191413</td>
      <td>28.856210</td>
      <td>174.488476</td>
      <td>6.412103</td>
      <td>20.894912</td>
      <td>9.790434</td>
      <td>11.664797</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Germany</td>
      <td>DEU</td>
      <td>52.509692</td>
      <td>13.404760</td>
      <td>1.070305</td>
      <td>1.175923</td>
      <td>1.626645</td>
      <td>55.959551</td>
      <td>333.784591</td>
      <td>1052.295666</td>
      <td>5.021509</td>
      <td>11.711717</td>
      <td>19.765971</td>
      <td>133.834029</td>
      <td>5.964748</td>
      <td>18.804577</td>
      <td>6.690209</td>
      <td>8.054254</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Greece</td>
      <td>GRC</td>
      <td>37.981415</td>
      <td>23.733592</td>
      <td>1.135081</td>
      <td>1.310484</td>
      <td>2.052419</td>
      <td>49.975806</td>
      <td>323.794355</td>
      <td>1078.937500</td>
      <td>11.669355</td>
      <td>28.881048</td>
      <td>49.016129</td>
      <td>272.580645</td>
      <td>6.479022</td>
      <td>21.589196</td>
      <td>17.211694</td>
      <td>20.135081</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Ireland</td>
      <td>IRL</td>
      <td>53.345182</td>
      <td>-6.255522</td>
      <td>1.258310</td>
      <td>1.286704</td>
      <td>1.738227</td>
      <td>83.436288</td>
      <td>481.063712</td>
      <td>1663.505540</td>
      <td>9.189751</td>
      <td>22.608033</td>
      <td>38.332410</td>
      <td>176.288089</td>
      <td>5.765641</td>
      <td>19.937435</td>
      <td>13.418283</td>
      <td>15.724377</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Italy</td>
      <td>ITA</td>
      <td>42.626023</td>
      <td>12.363507</td>
      <td>1.176970</td>
      <td>1.338835</td>
      <td>2.401121</td>
      <td>74.491280</td>
      <td>485.699938</td>
      <td>1559.972127</td>
      <td>11.973061</td>
      <td>28.887730</td>
      <td>48.825600</td>
      <td>264.498754</td>
      <td>6.520225</td>
      <td>20.941674</td>
      <td>16.914668</td>
      <td>19.937870</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Netherlands</td>
      <td>NLD</td>
      <td>52.365621</td>
      <td>4.887895</td>
      <td>1.052458</td>
      <td>1.165077</td>
      <td>1.601614</td>
      <td>108.778430</td>
      <td>627.061629</td>
      <td>2064.720470</td>
      <td>2.322817</td>
      <td>7.236977</td>
      <td>14.302274</td>
      <td>113.137197</td>
      <td>5.764577</td>
      <td>18.980973</td>
      <td>4.914160</td>
      <td>7.065297</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Spain</td>
      <td>ESP</td>
      <td>40.654117</td>
      <td>-0.838517</td>
      <td>1.238249</td>
      <td>1.355661</td>
      <td>2.050999</td>
      <td>63.853473</td>
      <td>397.508658</td>
      <td>1260.939486</td>
      <td>8.328449</td>
      <td>20.654044</td>
      <td>36.138535</td>
      <td>224.251951</td>
      <td>6.225326</td>
      <td>19.747391</td>
      <td>12.325595</td>
      <td>15.484491</td>
    </tr>
    <tr>
      <th>11</th>
      <td>United Kingdom</td>
      <td>GBR</td>
      <td>52.216874</td>
      <td>-0.642194</td>
      <td>1.153336</td>
      <td>1.180243</td>
      <td>1.524143</td>
      <td>69.830446</td>
      <td>435.758938</td>
      <td>1556.371176</td>
      <td>12.777000</td>
      <td>27.625138</td>
      <td>44.446369</td>
      <td>201.544047</td>
      <td>6.240243</td>
      <td>22.287860</td>
      <td>14.848139</td>
      <td>16.821231</td>
    </tr>
    <tr>
      <th>12</th>
      <td>United States</td>
      <td>USA</td>
      <td>38.148298</td>
      <td>-99.842362</td>
      <td>1.121588</td>
      <td>1.051515</td>
      <td>1.397903</td>
      <td>93.455625</td>
      <td>567.163644</td>
      <td>1936.522745</td>
      <td>10.569079</td>
      <td>25.022655</td>
      <td>42.031331</td>
      <td>211.301500</td>
      <td>6.068802</td>
      <td>20.721308</td>
      <td>14.453576</td>
      <td>17.008676</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>When we focus on the pricing strategy of Airbnb listings, it is interesting to note that the daily price is competing with the hotels while the monthly price is competing with the property leasing (house rental market).</p>
<p>Daily price is a little bit lower than daily hotel price.<br>
The range of weekly price is from 5.7 to 6.5 times of daily price. Mainly focus on this section of market.<br>
The range of monthly price is from 18.8 to 22.3 times of daily price. A little bit higher than monthly leasing price.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[57]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">sns</span><span class="o">.</span><span class="n">lmplot</span><span class="p">(</span><span class="s1">&#39;Price&#39;</span><span class="p">,</span> <span class="s1">&#39;Weekly Price&#39;</span><span class="p">,</span> <span class="n">airbnb_pricing_plot</span><span class="p">)</span>
<span class="n">pp</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[58]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">sns</span><span class="o">.</span><span class="n">lmplot</span><span class="p">(</span><span class="s1">&#39;Next Month&#39;</span><span class="p">,</span> <span class="s1">&#39;Next 2nd Month&#39;</span><span class="p">,</span> <span class="n">airbnb_pricing_plot</span><span class="p">)</span>
<span class="n">pp</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="bedrooms,-bathrooms,-and-beds-&lt;-&gt;-Price?">bedrooms, bathrooms, and beds &lt;-&gt; Price?<a class="anchor-link" href="#bedrooms,-bathrooms,-and-beds-&lt;-&gt;-Price?">&#182;</a></h3><p>We've tried bedrooms, bathrooms, and beds. Afterthat we find the most clear relation is Price ~ Beds, w.r.t Room Type. With more beds, entire apt has a higher price setting, then is Private room, and the lowest price is Shared room.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[59]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">airbnbAreaLmplot</span><span class="p">(</span><span class="n">by</span><span class="o">=</span><span class="s1">&#39;Country Code&#39;</span><span class="p">,</span> <span class="n">area</span><span class="o">=</span><span class="s1">&#39;USA&#39;</span><span class="p">):</span>
    <span class="n">airbnb_area</span> <span class="o">=</span> <span class="n">airbnb_pricing</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">airbnb_p</span><span class="p">[</span><span class="n">by</span><span class="p">]</span><span class="o">==</span><span class="n">area</span><span class="p">,</span> <span class="p">:]</span>
    <span class="n">ax</span> <span class="o">=</span> <span class="n">sns</span><span class="o">.</span><span class="n">lmplot</span><span class="p">(</span><span class="n">data</span><span class="o">=</span><span class="n">airbnb_area</span><span class="p">,</span> <span class="n">x</span><span class="o">=</span><span class="s1">&#39;Beds&#39;</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">&#39;Price&#39;</span><span class="p">,</span> <span class="n">hue</span><span class="o">=</span><span class="s1">&#39;Room Type&#39;</span><span class="p">,</span> <span class="n">height</span><span class="o">=</span><span class="mi">7</span><span class="p">)</span>
    <span class="c1"># ax.set(yscale=&quot;log&quot;)</span>
    <span class="n">pp</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Guess-the-reason:">Guess the reason:<a class="anchor-link" href="#Guess-the-reason:">&#182;</a></h3><p>As the bedroom is fixed,<br>
(positive slope) more beds in a shared room is terrible, different persons will live in one room<br>
(very flat, nearly zero slope) if it is a private room, it will not influence so much<br>
(negative slope) if it is an entire apt, more beds are more convenient</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[60]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># in the USA</span>
<span class="n">airbnbAreaLmplot</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAlsAAAHsCAYAAADl4mghAAAABHNCSVQICAgIfAhkiAAAAAlwSFlzAAALEgAACxIB0t1+/AAAADl0RVh0U29mdHdhcmUAbWF0cGxvdGxpYiB2ZXJzaW9uIDMuMC4yLCBodHRwOi8vbWF0cGxvdGxpYi5vcmcvOIA7rQAAIABJREFUeJzs3Xt0VOWh/vHvnpmdSQgxCSThJqFCrbRisEiNCOKNFqgiLXpOqy0ue84p6hG1tfATBaFQFVAq3q3W2q5SVistQihCqKfW1ltRsDqyxKIoBAQhCUnIhbntvX9/TAhJCLfJ7CQzeT5rseK8zLzzvgOGJ+/VcBzHQURERERc4ensBoiIiIikMoUtERERERcpbImIiIi4SGFLRERExEUKWyIiIiIuUtgSERERcZHCloiIiIiLFLZEREREXKSwJSIiIuIihS0RERERFylsiYiIiLhIYUtERETERb7OboDbKivrsO3OvWs7N7cHVVUNndqGREu1PqVafyD1+pRq/YHU61Oq9Qfc6VN+flZC65OuTyNbHcDn83Z2ExIu1fqUav2B1OtTqvUHUq9PqdYfSM0+ScdT2BIRERFxkcKWiIiIiIsUtkRERERcpLAlIiIi4iKFLREREREXKWyJiIiIuEhhS0RERMRFClsiIiIiLlLYEhEREXGRwpaIiIiIixS2RERERFyksCUiIiLiIoUtERERERcpbImIiIi4yNWwVVdXx5VXXsnu3bsBeOONN5g0aRLf+MY3WLp0adPztm7dypQpUxg/fjyzZ88mGo0CsGfPHr73ve8xYcIEbr75Zurr691sroiIiEjCuRa23nvvPa699lp27NgBQDAY5O677+bJJ59k3bp1bNmyhb///e8AzJw5k7lz57JhwwYcx2HFihUAzJ8/n+uuu47S0lKGDRvGk08+6VZzRURERFzhWthasWIF8+bNo6CgAIBAIMCgQYMYOHAgPp+PSZMmUVpaymeffUYwGOTcc88FYMqUKZSWlhKJRHj77bcZP358i3IRERGRZOJzq+L77ruvxeP9+/eTn5/f9LigoIB9+/YdVZ6fn8++ffuoqqqiZ8+e+Hy+FuUiiRQpCxAJrKesvhInszdm0UTMwqLObpaIiKQQ18JWa7ZtYxhG02PHcTAM45jlh7821/rxyejdu2f8jU6g/Pyszm5CwiV7n+q3v0PlP5djeH0Y6T0hdJDoP5eTnZNB5pARnd28hEj2P6PWUq0/kHp9SrX+QGr2STpWh4Wtvn37Ul5e3vS4vLycgoKCo8orKiooKCigV69e1NbWYlkWXq+36fmnqrKyDtt2EtKHeOXnZ1FeXtupbUi0VOhTwz9ewHY8GIaJzzCwDBPHsan4xws0nHZmZzev3VLhz6i5VOsPpF6fUq0/4E6fFN66nw47+mH48OF8+umn7Ny5E8uyWLt2LWPHjmXAgAH4/X42b94MQElJCWPHjsU0TUaOHMm6desAWL16NWPHju2o5ko3YNeWgy+tZaEvLVYuIiKSIB02suX3+1m0aBG33noroVCIiy++mAkTJgCwZMkS5syZQ11dHWeffTbXX389APPmzWPWrFk89dRT9OvXj4ceeqijmivdgCcrH7u+Gkz/kcJoGE9W/rFfJCIicooMx3E6d47NZZpGdEcq9ClSFiD0+jLw+PClZxANHgI7in/01JRYJJ8Kf0bNpVp/IPX6lGr9AU0jSmLoBHnptszCIvyjp+LJzMEJ1uHJzEmZoCUiIl1Hh00jinRFZmERZmFRSv5ELiIiXYNGtkRERERcpLAlIiIi4iKFLREREREXKWyJiIiIuEhhS0RERMRFClsiIiIiLlLYEhEREXGRwpaIiIiIixS2RERERFyksCUiIiLiIoUtERERERcpbImIiIi4SGFLRERExEUKWyIiIiIuUtgSERERcZHCloiIiIiLFLZEREREXKSwJSIiIuIihS0RERERFylsiYiIiLhIYUtERETERQpbIiIiIi5S2BIRERFxkcKWiIiIiIsUtkRERERc5OvsBkjni5QFiATWY9eW48nKxyyaiFlY1NnNEhERSQka2ermImUBQq8vw66vhrRM7PpqQq8vI1IW6OymiYiIpASFrW4uElgPHh+G6ccwDAzTDx5frFxERETaTWGrm7Nry8GX1rLQlxYrFxERkXZT2OrmPFn5EA23LIyGY+UiIiLSblog382ZRRMJvb4MJ0JshCsaBjuKWTSxs5vWIQ5vDiirr8TJ7K3NASIiknAa2ermzMIi/KOn4snMgXA9nswc/KOndovA0XxzgJHeU5sDRETEFRrZEszCom4Rrlpra3OAE4mVd8fPQ0RE3KGRLem2tDlAREQ6gsKWdFvaHCAiIh1BYUu6LbNoIthRnEgIx3FwIqFutTlAREQ6hsKWdFvNNwc4wbputTlAREQ6jhbIS7d2eHNAfn4W5eW1nd0cERFJQRrZEhEREXGRwpaIiIiIixS2RERERFyksCUiIiLiIoUtERERERcpbImIiIi4SGFLRERExEUKWyIiIiIuUtgSERERcZHCloiIiIiLFLZEREREXKSwJSIiIuIihS0RERERFylsiYiIiLhIYUtERETERQpbIiIiIi5S2BIRERFxkcKWiIiIiIsUtkRERERcpLAlIiIi4iKFLREREREXKWyJiIiIuEhhS0RERMRFClsiIiIiLlLYEhEREXGRwpaIiIiIixS2RERERFyksCUiIiLiIoUtERERERcpbImIiIi4SGFLRERExEUKWyIiIiIu8nXGm5aUlPDMM88AMHbsWO688062bt3K7Nmzqa+vZ+TIkcyfPx+fz8eePXuYOXMmlZWVnHHGGSxZsoTMzMzOaHaXENheQenGMipqguRlpzOhuJCiIXmd3SwRERE5hg4f2Tp06BD33Xcfy5Yto6SkhE2bNvHGG28wc+ZM5s6dy4YNG3AchxUrVgAwf/58rrvuOkpLSxk2bBhPPvlkRze5ywhsr2D5S9uorg/TI91HdX2Y5S9tI7C9orObJiIiIsfQ4WHLsixs2+bQoUNEo1Gi0Sg+n49gMMi5554LwJQpUygtLSUSifD2228zfvz4FuXdVenGMrxeD37Ti2EY+E0vXq+H0o1lnd00EREROYYOn0bs2bMnt99+OxMnTiQjI4Ovfe1rmKZJfn5+03Py8/PZt28fVVVV9OzZE5/P16L8VPTu3TOh7Y9Xfn5Wu+s4UBcmK8OHYRhNZT6vQVVdOCH1n6rOeE83pVp/IPX6lGr9gdTrU6r1B1KzT9KxOjxsffjhh6xcuZK//e1vZGVlMWPGDF5//fUWAcJxHAzDaPraXOvHJ1JZWYdtOwlpe7zy87MoL69tdz29eqZRXR/Gb3qbykIRi9yeaQmp/1Qkqk9dRar1B1KvT6nWH0i9PqVaf8CdPim8dT8dPo342muvMWrUKHr37k1aWhpTpkxh48aNlJeXNz2noqKCgoICevXqRW1tLZZlAVBeXk5BQUFHN7nLmFBciGXZhCIWjuMQilhYls2E4sLObpqIiIgcQ4eHraFDh/LGG2/Q0NCA4zi8/PLLnH/++fj9fjZv3gzEdiuOHTsW0zQZOXIk69atA2D16tWMHTu2o5vcZRQNyeN7X/8SOZlpNASj5GSm8b2vf0m7EUVERLqwDp9GHDNmDB988AFTpkzBNE3OOeccpk2bxte//nXmzJlDXV0dZ599Ntdffz0A8+bNY9asWTz11FP069ePhx56qKOb3KUUDclTuBIREUkihuM4nbugyWWptGarK0m1PqVafyD1+pRq/YHU61Oq9Qe0ZksSQyfIi4iIiLhIYUtERETERQpbIiIiIi5S2BIRERFxkcKWiIiIiIsUtkRERERcpLAlIiIi4iKFLREREREXKWyJiIiIuEhhS0RERMRFClsiIiIiLurwi6ilfQLbKyjdWEZFTZC87HQmFBe2+2LqSFmASGA9dm05nqx8zKKJmIVFCWpx4iRLO0VERJrTyFYSCWyvYPlL26iuD9Mj3Ud1fZjlL20jsL0i7jojZQFCry/Drq+GtEzs+mpCry8jUhZIYMvbL1naKSIi0prCVhIp3ViG1+vBb3oxDAO/6cXr9VC6sSzuOiOB9eDxYZh+DMPAMP3g8cXKu5BkaaeIiEhrCltJpKImSJqv5R9Zms9DRU0w7jrt2nLwpbUs9KXFyruQZGmniIhIawpbSSQvO51w1G5RFo7a5GWnx12nJysfouGWhdFwrLwLSZZ2ioiItKawlUQmFBdiWTahiIXjOIQiFpZlM6G4MO46zaKJYEdxIiEcx8GJhMCOxsq7kGRpp4iISGvajZhEDu86TORuxNhuvqldfpdfsrRTRESkNYWtJFM0JK/dRz20ZhYWJUVoSZZ2ioiINKdpRBEREREXKWyJiIiIuEhhS0RERMRFClsiIiIiLlLYEhEREXGRwpaIiIiIixS2RERERFyksCUiIiLiIoUtERERERcpbImIiIi4SGFLRERExEUKWyIiIiIu0kXUQmB7BaUby6ioCZKXnc6E4sKEX3YtIiLSXSlsdXOB7RUsf2kbXq+HHuk+quvDLH9pG4ACl4iISAJoGrGbK91YhtfrwW96MQwDv+nF6/VQurGss5smIiKSEhS2urmKmiBpvpZ/DdJ8Hipqgp3UIhERkdSisNXN5WWnE47aLcrCUZu87PROapGIiEhqUdjq5iYUF2JZNqGIheM4hCIWlmUzobiws5smIiKSErRAvps7vAheuxFFRETcobAlFA3JU7gSERFxiaYRRURERFyksCUiIiLiIoUtERERERcpbImIiIi4SGFLRERExEUKWyIiIiIuUtgSERERcZHCloiIiIiLFLZEREREXKSwJSIiIuIihS0RERERFylsiYiIiLhIYUtERETERQpbIiIiIi5S2BIRERFxkcKWiIiIiIsUtkRERERcpLAlIiIi4iKFLREREREXKWyJiIiIuEhhS0RERMRFClsiIiIiLvJ1dgNETlakLEAksB67thxPVj5m0UTMwqLObpaIiMhxaWRLkkKkLEDo9WXY9dWQloldX03o9WVEygKd3TQREZHjUtiSpBAJrAePD8P0YxgGhukHjy9WLiIi0oUpbElSsGvLwZfWstCXFisXERHpwhS2JCl4svIhGm5ZGA3HykVERLowhS1JCmbRRLCjOJEQjuPgREJgR2PlIiIiXZjCliQFs7AI/+ipeDJzIFyPJzMH/+ip2o0oIiJdno5+kKRhFhYpXImISNLRyJaIiIiIixS2RERERFzUKdOIL7/8Mo8//jiHDh1i9OjRzJkzhzfeeIOFCxcSCoWYOHEiP/7xjwHYunUrs2fPpr6+npEjRzJ//nx8vu47+xnYXkHpxjIqaoLkZaczobiQoiF57aozuLmEyPsbIBIEMx3znPGknzc5QS0WERHp3jp8ZGvXrl3MmzePJ598kjVr1vDBBx/w97//nbvvvpsnn3ySdevWsWXLFv7+978DMHPmTObOncuGDRtwHIcVK1Z0dJO7jMD2Cp57cSuf7DlIVW2IT/Yc5LkXtxLYXhF3ncHNJUTeKYFoCAwvRENE3ikhuLkkgS0XERHpvjo8bL300kt885vfpG/fvpimydKlS8nIyGDQoEEMHDgQn8/HpEmTKC0t5bPPPiMYDHLuuecCMGXKFEpLSzu6yV3Gn/72MfXBKLbj4DHAdhzqg1H+9LeP464z8v4GMAzweMHT+NUwYuUiIiLSbh0+H7dz505M0+Smm25i7969XHLJJZx55pnk5x85nLKgoIB9+/axf//+FuX5+fns27fvlN6vd++eCWt7e+TnZ7W7jn3VwVge8hzJyLZts686GHf9tZEgeLwYGE1ljuGByInrTESfupJU6w+kXp9SrT+Qen1Ktf5AavZJOlaHhy3Lsti0aRPLli2jR48e3HzzzaSnp2MYzf6xdxwMw8C27TbLT0VlZR227SSs/fHIz8+ivLy2/RU5DrYDhnOkP7YDHpz46zfTIRrCaf65OjaY6cetM2F96iJSrT+Qen1Ktf5A6vUp1foD7vRJ4a376fBpxLy8PEaNGkWvXr1IT09n3LhxvPHGG5SXH7njrry8nIKCAvr27duivKKigoKCgo5ucpfRp1cPIBa4gMavTmN5fMxzxoPjgG3FKrQtcJxYuYiIiLRbh4etSy+9lNdee42DBw9iWRavvvoqEyZM4NNPP2Xnzp1YlsXatWsZO3YsAwYMwO/3s3nzZgBKSkoYO3ZsRze5y7jmkiFkZqThMcCybTwGZGakcc0lQ+KuM/28yZgjJoPPD44FPj/miMnajSgiIpIgHT6NOHz4cP7nf/6H6667jkgkwujRo7n22msZPHgwt956K6FQiIsvvpgJEyYAsGTJEubMmUNdXR1nn302119/fUc3ucsoGpLHf31zaMKPfkg/T+FKRETELYbjOJ27oMllKbVmqwtJtT6lWn8g9fqUav2B1OtTqvUHtGZLEkMnyIuIiIi4SGFLRERExEUKWyIiIiIuUtgSERERcZHCloiIiIiLFLZEREREXKSwJSIiIuIihS0RERERFylsiYiIiLhIYUtERETERQpbIiIiIi7q8IuopX0C2ysSfhF1pCxAJLAeu7YcT1Y+ZtFEzMKiBLU4cZKlnSIiIs1pZCuJBLZXsPylbVTXh+mR7qO6Pszyl7YR2F4Rd52RsgCh15dh11dDWiZ2fTWh15cRKQsksOXtlyztFBERaU1hK4mUbizD6/XgN70YhoHf9OL1eijdWBZ3nZHAevD4MEw/hmFgmH7w+GLlXUiytFNERKQ1ha0kUlETJM3X8o8szeehoiYYd512bTn40loW+tJi5V1IsrRTRESkNYWtJJKXnU44arcoC0dt8rLT467Tk5UP0XDLwmg4Vt6FJEs7RUREWlPYSiITiguxLJtQxMJxHEIRC8uymVBcGHedZtFEsKM4kRCO4+BEQmBHY+VdSLK0U0REpDXtRkwih3cdJnI3Ymw339Quv8svWdopIiLSmsJWkikaktfuox5aMwuLkiK0JEs7RUREmlPYEhER6aY2btzILbfcwoABAzAMg2AwSN++fXnkkUfIzs527X1vuOEGqqqqqKiowOv1kpuby6BBg3j00Udde8/OpLAlIiLSjV144YUtQs7ChQtZsWIFP/zhD117z9/85jcAPPbYY+Tm5vL973/ftffqChS2REREBIBoNEp5eTmDBw8G4MUXX+Spp57CMAyuvPJKbrzxRiKRCHPmzOGDDz7A7/czb948zjnnHK644grOP/98Nm7cyPDhwxk8eDBr164lNzeXZ599Fp/vxJHjjjvuYPLkyVx88cUcOHCA//7v/2bWrFk8++yzNDQ0UF5ezg9+8AOuvfZa6urqmD17Nrt27SIjI4MFCxYwZMgQtz+iuJzUbkTbtnn22We58847qaur4+mnn8ayLLfbJiIiIi574403mDx5Mpdeeinf+MY3GDRoEFdffTX79+/n0Ucf5Xe/+x0rV67klVdeYdOmTSxfvpyMjAz+/Oc/c++99zJz5kwcx+HQoUOcd955rF27lk2bNpGenk5JSQmWZfHuu++eVFuuvPJK1q1bB8Bf/vIXxo8fD8B7773Hww8/zMqVK/nVr37F559/zhNPPMEVV1zBCy+8wN133828efNc+4za66TC1gMPPMC2bdsIBGJXo7z66qssXLjQ1YaJiIiI+y688EJKSkp4/vnnMU2TCy64AJ/Px5YtWzj//PPJyckhLS2NiRMn8tZbb7F582auuuoqAIYOHUpGRgb79u0DYMyYMXg8Hvr27cvIkSMBGDBgALW1tSfVlosuuohNmzYRDodZt24dV1xxBQCjR48mPz+frKwsLrzwQv71r3+xceNGHnvsMSZPnszdd9/N3r17Xfh0EuOkphHffPNNVq1axZQpU+jZsyfPPfcckydPdrttIiIi0kEKCgqYOXMmc+bM4cUXX8S2Wx6i7TgOlmUdNbPlOA7RaBQA0zSbyr1e7ym3wTRNRo8ezdq1awmHwwwcOJA9e/a0mIJ0HAev14tlWTz99NP0798foCnwdUUnNbLl8/nweI48NS0t7aTmXkVERCR5jBs3jpycHFatWsU555zDP//5T6qrqwmHw5SWlvLVr36VkSNHsmbNGgA+/PBDDh482BR4EmHSpEk89NBDTJgwoansn//8JwcPHuTgwYNs3LiRESNGMGLECP74xz8C8PLLL/PjH/84YW1ItJNKTF/60pdYvnw5lmXxySef8Jvf/IahQ4e63TYRERHpYNOnT2f+/PlMmTKFW2+9lalTpxKJRJg4cSJjxoxh5MiRzJs3j0mTJuH1ennggQdaDMi018iRI7Ftm4kTj9wQ0rt3b6ZNm0ZNTQ233HILeXl53Hbbbdx9991MmjQJv9/PokWLEtaGRDMcx3FO9KS6ujruv/9+XnnlFWzbZsyYMcyePZvc3NyOaGO7VFbWYdsn7KKr8vOzKC8/ufnqZJFqfUq1/kDq9SnV+gOp16dU6w+406f8/KyE1pdKHMfh3//+Nw888ADPPfccEDsLbPny5Ul9BtdJjWz17NmTm2++mfvvv5+6ujrKysqSImiJiIhI8li5ciWPPPIITz31VGc3JaFOatxv2bJl/O///i8AVVVV3HrrrU3zpCIiIiKJcM011/Dqq68ybNiwprLi4uKkHtWCkwxbzz//PL///e8BGDhwIKtXr+a3v/2tqw0TERERSQUnNY1oWRY9e/ZsepyVlYVhGK41So7t/557kmHhd0k3IgQdky1p5zLuv/63XXXWv/w09vaN4NhgePAMKSbzshu7XJ2RsgCRwHrs2nI8WfmYRRPbfTH14TrL6itxMnsnpE4REZHmTmpka/DgwSxZsoRdu3axa9cuHnnkEb7whS+43DRp7f+ee5KRkbfxG1GiGPiNKCMjb/N/zz0Zd531Lz+N/fGbsVAE4NjYH79J/ctPd6k6I2UBQq8vw66vhrRM7PpqQq8vI1IWSEidRnrPhNTplkhZgIa1i6n7/Qwa1i7ukm0UEZG2nVTYmj9/Pjt27OBb3/oW11xzDTt27OCnP/2py02T1oaF38XBwMKAxq8OBsPCJ3cNQlvs7Rsb/8to9qt5edeoMxJYDx4fhunHMAwM0w8eX6y8C9XpBjeCpoiIdJyTmkbMy8vj8ccfd7stcgLpRoQoLadvrcbyuDn2qZV3Up12bTmkZbYs9KXFyrtQnW5oHgoBMP04kVi5pjxFJBF2797NhAkTGDJkCIZhEIlEKCgoYOHChfTt27fFc/ft28ecOXP45S9/ecrvc9dddzF9+nQGDBiQqKYnheOGrfvuu4/Zs2dz0003tfn7v/jFL1xplLQt6Jj4jSjNL0rwNpbHzfC0HYKMdhxQ50Kdnqz82MjO4cABEA3jycrvUnW6IVlCoYgkt4KCAkpKSpoeL1q0iAceeICHHnqoxfP69OkTV9CC2JlZt9xyS7vamYyOG7ZGjRoF0HTrtnSuV8Nf5uv+AF5iI1pewMDh1fCX+Y846/QMKY6tr8I5qjxebtRpFk0k9PoynAjgS4NoGOwoZtHEE772ZOp0vBk4kVC763RDsoRCEekYm7bu44VXPmbfgQb69OrBlEu+yMgv90n4+xQXFzcFrcsuu4yioiK2bt3Kgw8+yI9+9CNWrlzJlVdeySuvvIJpmmzbto0ZM2awZs0ali5dyptvvklNTQ0FBQUsXbqUF154gf379zNt2jSWL1/Orl27WLhwIcFgkNzcXObPn8/AgQNbtGHq1KlkZ2fz0Ucf8fDDD/P555/z8MMPY9s2AwcOZMGCBeTl5fHuu+9y3333EQqFyM3NZcGCBQwaNIipU6fyla98hc2bNxMKhZgxYwa//e1v2b59OzfccAM33HBDwj+3thx3qOGyyy4DYPXq1Xz7298+6pd0rLOumErpoSJCjg8fDiHHR+mhIs66YmrcdWZediOeL446MupkePB8cVS7dg66UadZWIR/9FQ8mTkQrseTmYN/9NR2TaM1r9MJ1iWkTjeYRRPBjuJEQjiO02VDoYi4b9PWfTz9QoCqg4fIyvBRdfAQT78QYNPWxF7CHIlE2LBhA+eee25T2dixY9mwYQO9evUCIDc3l6KiIl577TUAXnzxRa666ip27tzJJ598wh/+8Ac2bNhAv379WLNmDdOmTaOgoIBnnnmGzMxM5syZw89//nNWrVrFD37wA+65554223LWWWexYcMGCgoKmDt3Lk888QR//vOfGTFiBAsWLCAcDnPHHXdwzz33sGbNGr773e9yxx13NL3ecRz+9Kc/MX78eO69914ef/xxli9fzhNPPJHQz+x4TmrNVm1tLQ0NDfTo0cPt9shxFA3Jg0lT+e3GMipqguRlpzPh64Wx8nbIvOxGaOexDB1Rp1lYlPAgdLjOrnzNSKzPUxN+7IWIJJ8XXvkYn88gPS32z3d6mo8gUV545eN2j27t37+fyZMnAxAOhykqKuInP/lJ0+8PHz78qNdcddVVvPjii1x66aWsX7+eZcuW0adPH+68807++Mc/8umnn/Luu+9SWFjY4nU7duxg165d3HzzzU1ldXV1bbarqCj2vS4QCFBUVMTpp58OwHe+8x2eeeYZduzYwWmnndb0vIkTJzJ37lxqa2Pf08eOHQtA//79GT58OBkZGQwYMICDBw/G9TnF46TCVkZGBpdeeilnnXVWi8ClNVsdr2hIXrvDlSQfN4KmiCSffQcayMpo+U+33/Sy/0BDu+tuvWarNb/ff1TZ5ZdfzqJFi3j77bfp168fffr0YcuWLfzkJz/hhhtuYPz48Xg8Hlpfw2zbNqeffnrT+1mWRUVFRZvvm56e3vSa5hzHIRqNHlV++PcsK7bC2TSPrGv2+U4q9iTcCVcsb9u2jcsvv5wbbriBb3/724wfP77pl4iIiHScPr16EIpYLcpCEYuCXp0z85SWlsZFF13E/fffz1VXXQXA22+/zfnnn8+1117LF77wBV555ZWm4OP1erEsi8GDB1NTU8OmTZuA2J2IM2bMOO57DR8+nPfee4/du3cDsdttiouLGTx4MNXV1QQCseNw1q1bR//+/cnJyXGr26fsuBFv5cqVLF68mEGDBlFWVsaSJUu46KKLOqoiUi9fAAAgAElEQVRtIiIi0syUS77I0y8ECBLFb3oJRSyiUYcpl3yx09o0efJk1qxZ0zQI881vfpPp06czadIkAIYNG9YUkC655BKmTZvGs88+yyOPPNK0qL1nz54sXrz4uO+Tl5fHggULmD59OpFIhP79+3PfffeRlpbG0qVL+dnPfsahQ4fIzs5m6dKl7nb6FBlO67G9Zr71rW/x9NNP06dPH/71r3+xdOnSpLsTsbKyDts+Zhc7RFdeDxSvVOtTqvUHUq9PqdYfSL0+pVp/wJ0+5edntev1h3cj7j/QQIGLuxElcU44edmnT+wP8Ktf/SpVVVWuN0hERESObeSX+yhcJZnjrtlqfdm01+t1tTEiIiIiqeaUjvRuHb5ERERE5PiOO43473//mxEjRjQ9DgaDjBgxAsdxMAyDd955x/UGioiIiCSz44atl156qaPaISIiIpKSjhu2utut3CIiIiKJdkprtkRERETk1ChsiYiIdHO7d+9m2LBhTJ48ucWv5cuXH/d1jz76aNMp8LNnz+b999+P6/1feOEFZs2aFddr47V69eoT9q8tgUCABx988JRe0zmXBEmXEtheQWnzy62L23+5tYiIJJcT3Y3Ylrfffpvi4mIA7rvvPjea5ZpXX32VH/3oR6f8uo8//pjKyspTeo3CVjcX2F7B8pe24fV66JHuo7o+zPKXtgEocImIdEH129+h5s0SotX78eUUkD1qMplDRpz4he0wZswYxo8fz+bNm/F6vTz88MNs3ryZLVu2MGfOHB5//HHuvfdepk+fDsCDDz6IbduceeaZzJ07lwULFvDRRx9hWRY//OEPufLKK496j507dzJ16lT27NnDqFGjuPfeewH4xS9+wZo1a/B6vYwePZqZM2eyd+9ebrnlFgYPHszHH3/MV77yFb761a+yatUqampqeOKJJxgyZAiBQICFCxcSDAbJzc1l/vz5DBw4ENu22bNnDwMHDuStt95i6dKlBINBDh48yF133cW4ceOYNWsWfr+f999/n/r6em6++WYuu+wyHn30URoaGnjqqae4+eabT+rzU9jq5ko3luH1evCbsQNr/aaXUGO5wpaISNdSv/0dKkufBa8PI70n0bqq2OMJ/9PuwLV//34mT57couyBBx7grLPOory8nFGjRnHPPfewaNEili9fzqxZs1i5ciXTp0/nrLPOavG6HTt28Le//Y2srCyWLFnC2WefzeLFi6mrq+O73/0uw4cPZ+DAgS1es3fvXlavXk2PHj0YN24cH330EXv27OHll19m5cqVmKbJrbfeyh/+8Acuvvhi/v3vf7Nw4UKGDh3K+PHjKSgo4Pnnn+fxxx/n+eefZ8aMGcyZM4df/OIX9O/fn1dffZV77rmH3/zmNwQCAc455xwAfve733HvvfcyZMgQ3nzzTe6//37GjRsHwK5du3j++eeprKxkypQpjB49mttuu4233nrrpIMWKGx1exU1QXqkt/xrkObzUFET7KQWiYjIsdS8WQJeHx4zHQDDTMcmSM2bJe0OWyeaRrzooosAOPPMM5vWaR3LGWecQVZW7A7IN954g2AwyMqVKwFoaGjgo48+OipsjRw5kpycHAAKCwupqqrin//8J1dccQUZGRkAXH311axevZqLL76YvLw8vvKVrwDQt29fRo0aBUD//v3ZvXs3O3bsYNeuXS1CUV1dHQD/+Mc/GDt2LBAbhfvb3/5GaWkp7733HvX19U3PnzJlCqZp0rdvX0aMGMHmzZuP2+9jUdjq5vKy06muDzeNbAGEozZ52emd2CoREWlLtHo/RnrPFmWGz0+0er/r7+33+2PvZxg4jnPc56anH/k3xLZtHnzwQc4++2wAKioqyM7OPuo1Pt+RSHL4PWzbPup50WgUgLS0tBblra8UtG2b008/vSlAWpZFRUUFEFtrduONNwJw3XXXUVxcTHFxMaNGjWLGjBlt1mnbdos2ngrtRuzmJhQXYlk2oYiF4ziEIhaWZTOhuLCzmyYiIq34cgpwoqEWZU40hC+noFPa4/V6sSzruM+54IIL+P3vfw/Epiqvuuoq9u7de1L1X3DBBbz4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4oorrsDFF1+MO++8E6ZpTsEoC+ehhx7C6tWrsXr1atx3332++8877zysXbsWa9eu9Z1ztXH11Vdj9erV7pj/8Ic/ePZv3boVa9aswUUXXYQHHnhgikZZGP/xH//hzmPt2rVYvnw51q1b5zmmlq7R2NgYLr30Uhw4cABAYdfi0KFD+MY3voGVK1fie9/7HqLR6GQOeVyy5/PEE0/g0ksvxZo1a3D77bdD1/WcczZu3IhzzjnHvV7V9h7MntPtt9+Oiy66yB3vCy+8kHNONX/vZc5ny5Ytns/TmWeeieuvvz7nnGq/RkSVIomycOTIEXneeefJwcFBGY1G5Zo1a+SuXbs8x6xevVq+8847Ukopb7/9drl+/fqpGGpBvPrqq/JP/uRPZDKZlLquy2uuuUY+//zznmOuv/56+fvf/36KRjhxhBDynHPOkYZh+O6Px+NyxYoVsqurSxqGIa+77jr5X//1X5M8yuLYuXOnvPDCC2V/f7+nvVau0bvvvisvvfRSedJJJ8n9+/cXfC2++93vymeeeUZKKeVDDz0k77vvvskeui/Z8/nkk0/khRdeKEdHR6UQQt56663yF7/4Rc5569atk08//fTkD7gAsuckpZSXXnqp7O7uHve8av3e85tPip6eHnn++efLPXv25JxXzdeIqF7IslUmtm7dijPPPBNNTU2IRCK4+OKLsXnzZnf/wYMHkUgkcOqppwIArrjiCs/+aqO9vR233XYbAoEANE3DokWLcOjQIc8x77//Pv7hH/4Ba9aswbp165BMJqdotIXxySefAACuu+46fPnLX8Yvf/lLz/7t27djwYIFmD9/PlRVxZo1a6r6GmVy99134+abb0ZLS4unvVau0YYNG3DXXXeho6MDQGHXwjAMvPXWW7j44osBVNdnKns+gUAAd911F+rr68EYw5IlS3I+TwDw3nvvYePGjVizZg1++MMfYnh4eLKHnpfsOcXjcRw6dAh33HEH1qxZgwcffBBCCM851fy9lz2fTO677z5cddVVWLhwYc6+ar5GRPVCYqtM9PT0oL293d3u6OhAd3d33v3t7e2e/dXG4sWL3S/IvXv34tlnn8WKFSvc/dFoFCeeeCJuueUWbNy4ESMjI/j7v//7qRpuQYyMjOCss87Cww8/jEcffRSPP/44Xn31VXf/0a5htbJ161YkEgmsWrXK015L1+hv//Zvcfrpp7vbhVyLwcFB1NfXQ1VVANX1mcqez7x58/D5z38eADAwMID169fj/PPPzzmvvb0df/7nf45f//rXmDt3bo5beCrJnlNfXx/OPPNM3HPPPdiwYQPefvttPPnkk55zqvl7L3s+Kfbu3Ys333wT11xzje951XyNiOqFxFaZEEKAMeZuSyk920fbX63s2rUL1113HW699VbPr7y6ujr80z/9ExYtWgRVVXHddddhy5YtUzfQAjjttNNw3333oaGhAS0tLfjKV77iGXOtXqPHH38c3/rWt3Laa/EapSjkWvi1Vfv16u7uxje/+U1ceeWVOOOMM3L2P/zww1i+fDkYY/jOd76D3/3ud1MwysKYP38+Hn74YXR0dCAcDuPqq6/OeX/V4mfqiSeewNe//nUEAgHf/bV0jYjqgcRWmZgzZw56e3vd7d7eXo95Ont/X1+fr/m6mti2bRuuvfZa/NVf/RUuv/xyz75Dhw55fsVKKV0LQ7Xy9ttv47XXXnO3s8d8tGtYjei6jrfeegtf+tKXcvbV4jVKUci1aGlpwejoKCzLyntMNbF7925cddVVuPzyy3HDDTfk7B8dHcWjjz7qbkspoSjKJI5wYnz00Ud47rnn3G2/91ctfu+99NJLuOSSS3z31do1IqoHEltl4uyzz8Zrr72GgYEBxONxPP/88zj33HPd/fPmzUMwGMS2bdsAAJs2bfLsrzYOHz6MG264Affffz+SkZCtAAAE2klEQVRWr16dsz8UCuHv/u7vsH//fkgpsX79elx44YVTMNLCGR0dxX333YdkMomxsTFs3LjRM+ZTTjkFe/bswb59+2BZFp555pmqvkaAfcNbuHAhIpFIzr5avEYpCrkWmqbh9NNPx29+8xsAwFNPPVW112tsbAzf/va38YMf/ADXXXed7zGRSAT//M//7K6Q/eUvf1nV10tKiXvuuQfDw8MwDANPPPFEznhr7XtvYGAAiUQC8+fP991fa9eIqB5IbJWJ2bNn4+abb8Y111yDyy67DJdeeimWLVuGP/uzP8N7770HALj//vvxk5/8BCtXrkQsFssbE1AN/PznP0cymcS9997rLnH+93//d3c+LS0tWLduHb73ve9h5cqVkFL6urKqifPOOw8rVqzAZZddhiuvvBJXXnklTjvtNKxduxbd3d0IBoO49957ceONN+KSSy7Bcccdh5UrV071sMdl//79mDNnjqetlq9RivGuxZ133omXXnoJAHDXXXdhw4YNuOSSS/D222/jpptumsph5+XJJ59EX18ffvGLX7ifp5/97GcA0vNRFAU//elPcffdd2PVqlX44IMPcMstt0zxyPOzdOlSfPe738XXvvY1rF69GieeeCIuvfRSAKjZ770DBw7kfJ6A2r1GRPXApJRyqgdBEARBEAQxXSHLFkEQBEEQRAUhsUUQBEEQBFFBSGwRBEEQBEFUEBJbBEEQBEEQFYTEFkEQBEEQRAWpjQyHBEGUlQMHDuDCCy/EkiVLANiZvkOhEG677TYsX7684H7WrVuH5uZm3HjjjZUaKkEQRM1DYosgZiihUAibNm1yt3/zm9/g9ttvx/PPPz+FoyIIgph+kNgiCAIAMDQ05BYNfvnll/HII4/AMAyEQiH89V//NU477TSMjY3hzjvvxI4dO9DR0QFFUVxL2L/927/h8ccfh6ZpCAaDWLduHY4//vipnBJBEERVQGKLIGYoiUQCa9euBQCMjIygt7cXDz/8MPbu3YsHHngA//qv/4rm5mbs2rUL3/rWt/D888/jwQcfRCgUwubNmzE4OIjLL78cy5cvh2VZuOeee/Dyyy+jo6MDTz31FLZt20ZiiyAIAiS2CGLGku1G3Lp1K2644Qb88Ic/RE9PD6699lp3H2MMXV1deO2113DHHXeAMYaWlha3LpyiKFi5ciWuuuoqfPGLX8Q555yDFStWTPaUCIIgqhISWwRBALCLqXd2dmJwcBBnnXUWfvrTn7r7Dh8+jI6ODgB2AeIUiqK4z++//37s3LkTW7duxT/+4z9i06ZNbv0/giCImQylfiAIAgCwZ88eHDx4EBdccAFeffVV7N69GwCwZcsWfPnLX0YikcAXvvAFPPnkkxBCYHh42C0IPTAwgBUrVqCpqQnXXnstbrrpJrcQMUEQxEyHLFsEMUPJjNkC7PQP69atw9KlS7Fu3Tr85V/+JaSUUFUVjzzyCOrq6nDjjTfirrvuwqpVq9DS0uKmjmhpacH3vvc9XHvttQiFQlAUBT/+8Y+namoEQRBVBZOZPgGCIAiCIAiirJAbkSAIgiAIooKQ2CIIgiAIgqggJLYIgiAIgiAqCIktgiAIgiCICkJiiyAIgiAIooKQ2CIIgiAIgqggJLYIgiAIgiAqCIktgiAIgiCICvL/Awba14wOWx3SAAAAAElFTkSuQmCC
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[61]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># A particular city</span>
<span class="n">airbnbAreaLmplot</span><span class="p">(</span><span class="s1">&#39;City&#39;</span><span class="p">,</span> <span class="s1">&#39;New York&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAlsAAAHsCAYAAADl4mghAAAABHNCSVQICAgIfAhkiAAAAAlwSFlzAAALEgAACxIB0t1+/AAAADl0RVh0U29mdHdhcmUAbWF0cGxvdGxpYiB2ZXJzaW9uIDMuMC4yLCBodHRwOi8vbWF0cGxvdGxpYi5vcmcvOIA7rQAAIABJREFUeJzs3Xl81PWh7//Xd7bsQoBEdlrUaquNqFREFFy4LCJig7fHavF672lVjmiPVioCYqEoityiVqv21HP8FWkrLSgUJehtK4WCC1hNPcWlIptSCEsg20xmvt/P749JJjPZSCDfTDLzfj4emMxnlu/nMxHmnc9qGWMMIiIiIuIKT7IrICIiIpLKFLZEREREXKSwJSIiIuIihS0RERERFylsiYiIiLhIYUtERETERQpbIiIiIi5S2BIRERFxkcKWiIiIiIsUtkRERERcpLAlIiIi4iKFLREREREX+ZJdAbcdOlSJ46TeWdv5+dkcOVKd7GokhdqutqcbtT212l5QkJfsKkgnU89WN+XzeZNdhaRR29OT2p6e0rntkjoUtkRERERcpLAlIiIi4iKFLREREREXKWyJiIiIuEhhS0RERMRFClsiIiIiLlLYEhEREXGRwpaIiIiIixS2RERERFyksCUiIiLiIoUtERERERcpbImIiIi4SGFLRERExEUKWyIiIiIuSkrY+uMf/0hxcTETJ05k4cKFAGzevJnJkyczbtw4li5dGnvs9u3bKS4uZvz48cyZM4dIJJKMKouIiIickE4PW3v27OGBBx7gZz/7GWvWrOHvf/87GzZsYPbs2fzsZz/j1Vdf5YMPPmDDhg0AzJw5k3nz5rF+/XqMMaxYsaKzq9yllH56kMW/epd/ffB1Fv/qXUo/PZjsKomIiEgrOj1svf7661x11VX07dsXv9/P0qVLycrKYsiQIQwaNAifz8fkyZMpKSnh888/JxgMMmzYMACKi4spKSnp7Cp3GaWfHmT56x9TXlVLXpaP8qpalr/+sQKXiIhIF+br7Avu2rULv9/Pbbfdxr59+7jssss444wzKCgoiD2msLCQ/fv3c+DAgYTygoIC9u/f39lV7jJK3tqN1+shw+/Fsiwy/F5CdeVFp/VJdvVERESkGZ0etmzbZuvWrSxbtozs7GymT59OZmYmlmXFHmOMwbIsHMdptrw9evfO7bC6J9vhymiPVv174Pd58HktjlTWUlCQl+Tada50a288tT09qe0i3Venh60+ffowcuRIevXqBcDYsWMpKSnB6/XGHlNWVkZhYSF9+/alrKwsVn7w4EEKCwvbdb1DhypxHNMxlU+yXrkByqtqyfB78fs8hCMOobBNfm6AsrKKZFev0xQU5KVVe+Op7Wp7uknFtis8pp9On7N1+eWXs2nTJo4dO4Zt22zcuJEJEybw2WefsWvXLmzbZu3atYwePZoBAwaQkZHBtm3bAFi9ejWjR4/u7Cp3GRNGDMa2owHLGEMobGPbDhNGDE521URERKQFnd6zde655/Ld736XG264gXA4zKhRo/j2t7/N0KFDueOOOwiFQowZM4YJEyYAsGTJEubOnUtlZSVnn302N910U2dXucuon5dV8tZujlTWkp8bYMKIwZqvJSIi0oVZxpjUGGNrQSoNI8ZLxa71tlLb1fZ0o7anVts1jJh+tIO8iIiIiIsUtkRERERcpLAlIiIi4iKFLREREREXKWyJiIiIuEhhS0RERMRFClsiIiIiLlLYEhEREXGRwpaIiIiIixS2RERERFyksCUiIiLiIoUtERERERcpbImIiIi4SGFLRERExEUKWyIiIiIuUtgSERERcZHCloiIiIiLFLZEREREXKSwJSIiIuIihS0RERERFylsiYiIiLhIYUtERETERQpbIiIiIi5S2BIRERFxkcKWiIiIiIsUtkRERERcpLAlIiIi4iKFLREREREXKWyJiIiIuEhhS0RERMRFClsiIiIiLlLYEhEREXGRwpaIiIiIixS2RERERFyksCUiIiLiIoUtERERERcpbImIiIi4SGFLRERExEUKWyIiIiIuUtgSERERcZHCloiIiIiLFLZEREREXKSwJSIiIuIihS0RERERFylsiYiIiLjIl4yLTps2jcOHD+PzRS+/YMECdu/ezdNPP00kEuF//a//xY033gjA5s2bWbRoEaFQiIkTJ3LXXXclo8oiIiIiJ6TTw5Yxhp07d/KnP/0pFrb279/PXXfdxapVqwgEAlx//fWMGDGCgQMHMnv2bJYtW0a/fv249dZb2bBhA2PGjOnsaksXEN5dSrh0HburDmFyeuMvmoh/cFGyqyUiItKqTg9bO3bsAOD//J//Q3l5Od/61rfIycnhoosuomfPngCMHz+ekpISLrzwQoYMGcKgQYMAmDx5MiUlJQpbaSi8u5TQX5aBx4cvMxe7qjx6m2kKXCIi0qV1+pytY8eOMXLkSJ566imef/55fvOb3/DFF19QUFAQe0xhYSH79+/nwIEDzZZL+gmXrgOPD8ufgWVZWP4M8Pii5SIiIl1Yp/dsnXfeeZx33nmx29dddx2LFi1i+vTpsTJjDJZl4TgOlmU1KW+P3r1zT77SXVRBQV6yq9BpdlcdwpeZG/v5+3xejDcLU3Uord4HSK+fe2Nqe3pK57ZLauj0sLV161bC4TAjR44EogFqwIABlJWVxR5TVlZGYWEhffv2bba8PQ4dqsRxTMdUvgspKMijrKwi2dXoNCanN3ZVOZY/A5/PSyRiY8IhPDm90+p9SLefezy1XW1PFQqP6afThxErKipYvHgxoVCIyspKXnrpJR599FG2bNnC4cOHqamp4bXXXmP06NGce+65fPbZZ+zatQvbtlm7di2jR4/u7CpLF+AvmghOBBMOYYzBhEPgRKLlIiIiXVin92xdfvnlvP/++1x77bU4jsMNN9zABRdcwF133cVNN91EOBzmuuuuo6goOun54Ycf5o477iAUCjFmzBgmTJjQ2VWWLiA6CX4a4dJ1mKpDeLQaUUREugnLGJN6Y2xxNIyYetR2tT3dqO2p1XYNI6Yf7SAvIiIi4iKFLREREREXKWyJiIiIuEhhS0RERMRFClsiIiIiLlLYEhEREXGRwpaIiIiIixS2RERERFyksCUiIiLiIoUtERERERcpbImIiIi4SGFLRERExEUKWyIiIiIuUtgSERERcZHCloiIiIiLFLZEREREXKSwJSIiIuIihS0RERERFylsiYiIiLhIYUtERETERQpbIiIiIi5S2BIRERFxkcKWiIiIiIsUtkRERERcpLAlIiIi4iKFLREREREXKWyJiIiIuEhhS0RERMRFClsiIiIiLlLYEhEREXGRwpaIiIiIixS2RERERFyksCUiIiLiIoUtERERERcpbImIiIi4SGFLRERExEUKWyIiIiIuUtgSERERcZHCloiIiIiLFLZEREREXKSwJSIiIuIihS0RERERFylsiYiIiLhIYUtERETERQpbIiIiIi5Kath65JFHmDVrFgDbt2+nuLiY8ePHM2fOHCKRCABffPEFN954IxMmTGD69OlUVVUls8oiIiIi7ZK0sLVlyxZeeuml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MHXqVA4cOMATTzzBCy+8wMqVK3njjTfYunUry5cvJysri9///vcsXLiQmTNnYoyhpqaGCy64gLVr17J161YyMzNZvXo1tm3z3nvvtakuV199Na+++ioAr732GuPHjwfg/fff57HHHmPlypU899xz/POf/+Spp55i0qRJrFq1itmzZ/PAAw+49h6drDaFrcWLF/Pxxx9TWhr9TXrjxo0sWrTI1YpJM8JBmv7IPHXlkqqcijLwBRILfYFouYjISbr44otZvXo1L774In6/n4suugifz8cHH3zAhRdeSM+ePQkEAkycOJG3336bbdu2cc011wBw1llnkZWVxf79+wG45JJL8Hg89O3bl+HDhwMwYMAAKioqWrx+vEsvvZStW7dSW1vLq6++yqRJkwAYNWoUBQUF5OXlcfHFF/PXv/6Vt956i5/+9KdMmTKF2bNns2/fPhfenY7RpjlbW7Zs4aWXXqK4uJjc3Fz+8z//kylT0mOeUJfiz4wOIeKNK3Si5ZKyPHkFOFXl4M9oKIzU4skrSF6lRCTlFBYWMnPmTObOncsrr7yC4zgJ9xtjsG27yciWMSY2TOj3+2PlXq+X9vL7/YwaNYq1a9dSW1vLoEGD+OKLL/D5GuKKMQav14tt2zz77LP0798fIBb4uqI29Wz5fD48noaHBgKBhIZL5/B/fTwYA46NMQ44NhgTLU91+QPbV55C/EUTwYlgwiGMMZhwCJxItFxEpAONHTuWnj178tJLL/H1r3+dN998k/LycmpraykpKeG8885j+PDhrFmzBoAPP/yQY8eOxQJPR5g8eTI/+clPmDBhQqzszTff5NixYxw7doy33nqL888/n/PPP5/f/va3APzxj3/krrvu6rA6dLQ2JaavfOUrLF++HNu22bFjB88//zxnnXWW23WTRupXHYb/tj46dJhGqxHz/udCKpb/AKoONRTm9E6L1YjRVYfTCJeuw1QdwqPViCLiohkzZjB//nyKi4u54447mDZtGuFwmIkTJ3LJJZcwfPhwHnjgASZPnozX62Xx4sUJHTIna/jw4TiOw8SJDb9Q9u7dm1tuuYWjR49y++2306dPH+68805mz57N5MmTycjI4OGHH+6wOnQ0yxhjjvegyspKHnroId544w0cx+GSSy5hzpw55Ofnd0YdT8qhQ5U4znGb2O0UFORRVta2MfBUUL8iD48P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cSP//u//3u7n/eMf/+DQoUPtek6nh619+/Zx++23s3TpUkaOHAlEzzv67LPP2LVrFwMHDmTt2rVMnTqVAQMGkJGRwbZt27jgggtYvXp17PTudFTleJsdMqxyvJyShPp0pmCPoWSVNxpKNBDsOZQeSatV5wjvLiX0l2Xg8eHLzMWuKo/eZlrKBy6nogwCOYmFvkC0XKRO/YCHqQtR4GA5TkKYcup7qpoJU91N1afvcnTLaiLlB/D1LKTHyCmu9/RecskljB8/nm3btuH1ennsscfYtm0bH3zwAXPnzuXJJ59k4cKFzJgxA4BHH30Ux3E444wzmDdvHgsWLOCTTz7Btm2+973vcfXVVze5xq5du5g2bRpffPEFI0eOZOHChQA888wzrFmzBq/Xy6hRo5g5c2YsSwwdOpR//OMffO1rX+O8887jpZde4ujRozz11FOcdtpplJaWsmjRIoLBIPn5+cyfP59BgwbhOA5ffPEFgwYN4u2332bp0qUEg0GOHTvGfffdx9ixY5k1axYZGRn87W9/o6qqiunTp3PFFVfwxBNPUF1dzdNPP8306dPb9P51eth67rnnCIVCCV2F119/PQ8//DB33HEHoVCIMWPGMGHCBACWLFnC3Llzqays5Oyzz+amm27q7Cp3GZXn30zWX5/DExc4HBMtT3W9Rl5LVcljeGg43d2xPPQaeW0Sa9U5wqXrwOPD8mdgWRaWPwMTjpanetjy5BXgVJWDP6OhMFKrw9fTTLRXCizs6D96xsYyTnS4z47roTIGpz5EdeMw1ZqqT9/lUMkvoG5oPVJ5JHp7wndPOnAdOHCAKVOmJJQtXryYM888k7KyMkaOHMn999/Pww8/zPLly5k1axYrV65kxowZnHnmmQnP27lzJ3/605/Iy8tjyZIlnH322TzyyCNUVlZy/fXXc+655zJo0KCE5+zbt4+XX36Z7Oxsxo4dyyeffMIXX3zBH//4R1auXInf7+eOO+7gN7/5DWPGjOGjjz5i0aJFnHXWWYwfP57CwkJefPFFnnzySV588UXuuece5s6dyzPPPEP//v3ZuHEj999/P88//zylpaWx4c4XXniBhQsXctppp7FlyxYeeughxo4dC8CePXt48cUXOXToEMXFxYwaNYo777yTt99+u81BC5IQtubOncvcuXObvW/NmjVNys466yx+97vfuV2tbiHy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tHoIDdPNz201fO69ic+9N/Xyc6fuIJRSqtWDICIiIupWXEYkIiIiaiAWW0REREQNxGKLiIiIqIFYbBERERE1EIstIiIiogZisUVERETUQCy2iIiIiBqIxRYRERFRA7HYIiIiImogFlsdaHFxEe9///tx5MiRVg+lqf7qr/4Ku3fvxu7du3HnnXe2ejhN961vfQtXXXUVdu/ejfvvv7/Vw2m6v/zLv8TNN9/c6mE01cc//nHs3r0b11xzDa655hrs27ev1UNqmscffxy/93u/h127duHrX/96q4dDdEq6/mzEbrNv3z7ceuutOHjwYKuH0lTPPPMMnnrqKTzwwAMQQuDTn/40fvSjH+G9731vq4fWFD//+c/x7LPP4t/+7d/gOA6uuuoq7Ny5E2eddVarh9YUe/fuxQMPPIDLL7+81UNpGqUUDh48iB//+McwjN76Uf3qq6/itttuww9+8AOMjIzgE5/4BJ588kns3Lmz1UMj2hDObHWY73//+7jtttuQy+VaPZSmymazuPnmmxGLxWCaJs4++2wcPXq01cNqmre+9a347ne/C8MwMD09Ddd1kUqlWj2spjh58iTuvvtufOYzn2n1UJrq5ZdfBgB86lOfwtVXX41/+Id/aPGImudHP/oRrrrqKoyPj8M0Tdx999248MILWz0sog3rrX8udYFvfOMbrR5CS5x77rnB2wcPHsQjjzyCf/qnf2rhiJrPNE3ce++9+Lu/+ztceeWVGBsba/WQmuJrX/savvSlL+HYsWOtHkpTzc/P45JLLsGf/dmfwbZt3HDDDTjzzDPxzne+s9VDa7hDhw7BNE185jOfwbFjx3D55Zfji1/8YquHRbRhnNmijrJ//3586lOfwpe//GXs2LGj1cNpus9//vPYu3cvjh07hu9///utHk7D/eAHP8Bpp52GSy65pNVDabqLLroId955J/r7+5HJZPChD30ITz75ZKuH1RSu62Lv3r2444478M///M944YUX8MADD7R6WEQbxmKLOsbzzz+PG2+8EX/0R3+E6667rtXDaaoDBw7g17/+NQAgmUzife97H1566aUWj6rxHn74YTz99NO45pprcO+99+Lxxx/HHXfc0ephNcVzzz2HvXv3Bu8rpXqmd2t0dBSXXHIJMpkMEokErrjiCrzwwgutHhbRhrHYoo5w7NgxfPazn8Vdd92F3bt3t3o4TXfkyBHceuutsCwLlmXhsccew8UXX9zqYTXc/fffj3//93/Hnj178PnPfx7vec97cMstt7R6WE2xsLCAO++8E6VSCYuLi3jggQd6ZkPIu9/9bjz11FOYn5+H67r46U9/igsuuKDVwyLasN74ZxJ1vL/9279FqVTCN7/5zeDa9ddfj4985CMtHFXz7Ny5Ey+88AKuvfZa6LqO973vfT1ZdPaSd7/73di3bx+uvfZaSCnx0Y9+FBdddFGrh9UUF154IT796U/jox/9KGzbxjvf+U588IMfbPWwiDZMKKVUqwdBRERE1K24jEhERETUQCy2iIiIiBqIxRYRERFRA7HYIiIiImogFltEREREDcToB6IedOTIEbz3ve/F6173OgCAlBKJRAI333zzuvK7br/9dgwPD+Omm25q1FCJiDoeiy2iHpVIJLBnz57g/Ycffhhf+cpX8Oijj7ZwVERE3YfFFhEBAE6ePIlsNgsAePzxx3HffffBtm0kEgn86Z/+KS666CIsLi7iq1/9Kl588UXkcjnouh7MhP3jP/4jvve978E0TcTjcdx+++0455xzWvmUiIjaAostoh5VLBZxzTXXAADm5+cxOTmJv/7rv8bBgwdx991347vf/S6Gh4exf/9+fPKTn8Sjjz6Ke++9F4lEAj/84Q8xOzuL6667DhdffDFc18Udd9yBxx9/HLlcDg8++CCef/55FltERGCxRdSzqpcRn3nmGXz2s5/FH//xH2NiYgI33nhj8DEhBA4fPoy9e/filltugRACmUwmOKtP13VceeWVuP7663H55ZfjXe96F3bu3Nnsp0RE1JZYbBERAOAd73gHtm/fjtnZWVxyySW45557go8dO3YMuVwOABA+4UvX9eDtu+66C7/5zW/wzDPP4G/+5m+wZ88efOtb32reEyAialOMfiAiAMArr7yC1157DVdccQWefvppHDhwAADw5JNP4uqrr0axWMSll16Kf/mXf4GUEnNzc3jssccAADMzM9i5cyeGhoZw44034otf/CJ+8YtftPLpEBG1Dc5sEfWocM8W4MU/3H777Tj//PNx++234w//8A+hlIJhGLjvvvuQTqdx00034bbbbsOuXbuQyWSC6IhMJoM/+IM/wI033ohEIgFd1/H1r3+9VU+NiKitCBVeEyAiIiKiTcVlRCIiIqIGYrFFRERE1EAstoiIiIgaiMUWERERUQOx2CIiIiJqIBZbRERERA3EYouIiIiogVhsERERETXQ/we0Tnmj+bEYgQAAAABJRU5ErkJggg==
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>In the same city, the comparison on the data will be more reasonable. As showed in the data of New York, it is more obvious to see the difference of slope.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[62]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># End. Thank you for reading.</span>
</pre></div>

    </div>
</div>
</div>

</div>
    </div>
  </div>
</body>

 


</html>

