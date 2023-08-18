---
title: "Resume"
permalink: /resume/
author_profile: true
---
<style>
* {
  box-sizing: border-box;
}

/* Create two equal columns that floats next to each other */
.column {
  float: left;
  width: 50%;
  padding: 10px;
}

/* Clear floats after the columns */
.row:after {
  content: "";
  display: table;
  clear: both;
}

iframe {
    display: block;
    aspect-ratio: 20/18;
    width: 85%;
    margin: 0 auto;
}
.aspect-ratio{
    position: relative;
    height: 0;
    padding-top: 90%;
}

</style>

<div class="row">
  <div class="column">
  <centering><h1>Polyglot Resume</h1></centering>
    <object data="../assets/files/resume/resume.pdf" width="100%" height="600" type='application/pdf'>
    <p>Unable to display PDF file. <a href="/assets/files/resume/resume.pdf">Download</a> instead.</p>
    </object>
    <center><a href="/assets/files/resume/resume.pdf">Download</a></center>
    <center><p>Executing this PDF opens a unique resume in a GameBoy emulator. For more information, either run it below or visit <a href="/projects/2023/08/04/resume.html">here</a> for a detailed explanation.</p></center>
  </div>
  <div class="column">
  <centering><h1>Gameboy Resume</h1></centering>
    <p align="center">
    <iframe
      id="emulator"
      title="GameBoy Emulator"
      src="/assets/files/resume/simple.html"
      allowfullscreen
    >
    </iframe>
    </p>
    <center><p><u><b>Press play</b></u></p><p><b>Click again</b> to activate controls and music.</p></center>
    </div>
</div>


