---
title: "About Page"
permalink: /about/
layout: single
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /assets/images/wallpaper.jpg
  actions:
    - label: "GitHub"
      url: "https://github.com/emorchy"
excerpt: "Welcome to my website!"
---
{% comment %}
You found a secret text! Gold star!
{% endcomment %}

<style>
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
</style>

My name is Ethan Morchy, and I am a hardware and software penetration tester with an emphasis on binary exploitation and cryptography. I enjoy making engineering projects and competing in CTFs.

<div class="row">
  <div class="column">
  <div markdown=1>
  This website is split into several pages: resume(s), writeups, talks, and projects. Navigate to any by clicking the links to the right or by visiting the top menu.

  If you wish to contribute to this website, pull requests are appreciated [here](https://github.com/emorchy/emorchy.github.io). Thank you.
  </div>
  </div>
  <div class="column">
  <div markdown=1>
# [Resume](/resume)
A polyglot PDF and a Gameboy web emulator.
# [Talks](/talks)
A collection of talks in various forms, from PDFs to videos to interactive slides.
# [Writeups](/writeups)
A collection of CTF writeups written by me. Includes competitions (e.g [PicoCTF](https://play.picoctf.org/users/aloevera)) and offline challenges (e.g [Cryptohack](https://cryptohack.org/user/emorchy/)).
# [Projects](/projects)
A beautiful conglomeration of computer software and embedded microcontrollers to engineer fun projects for myself and others.
  </div>
</div>
</div>
