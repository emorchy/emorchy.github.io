---
title: "Piezo Impact Sensor Shield"
category: projects
tag: engineering, piezo, arduino
excerpt: An impact sensor array for my little brother's shield to count deflected candy at his Bar Mitzvah.
---
<style>
img + em {
  display: block;
  text-align: center;
  margin: auto;
}
img.centered {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
img[alt=Bit-O-Honey] { width: 15%; margin: auto;}
img[alt=Shield of Daniel] { width: 50%; margin: auto;}
img[alt=Fritzing Model] { width: 50%; margin: auto;}
img[alt=Exposed] { width: 50%; margin: auto;}
img[alt=Covered] { width: 50%; margin: auto;}

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
    aspect-ratio: 1080/1920;
    width: 25%;
    margin: 0 auto;
}
.aspect-ratio{
    position: relative;
    height: 0;
    padding-top: 0%;
}
</style>

# What is a Bar Mitzvah?
A Bar Mitzvah is a Jewish rite of passage where a boy becomes a man in the eyes of Jewish talmudic law. 

er custom, the congregation throws candy after they finish a 10 minute chanting of a Hebrew scripture. Usually it is Bit-O-Honey.

![Bit-O-Honey](/assets/files/bar-mitzvah/bit-o-honey.png){:.centered}
<center><em>If God made a candy even</em> he <em>couldn't break.</em></center>

# Shield of Daniel
When my little brother Daniel's Bar Mitzvah rolled around several years later, he wanted something above and beyond as well. To block the candy, he crafted a wooden shield with a Jewish Star in the center. The humor is not lost on Hebrew-speaking people when the Jewish Star (known as the "Shield of David") is superglued on a shield for a child's Bar Mitzvah.

![Shield of Daniel](/assets/files/bar-mitzvah/shield-of-daniel.jpeg){:.centered}
*Shield of Daniel*

In a moment of "divine inspiration", I wondered how easy it could be to count how many candies were deflected by the shield.

## Engineering Parts
- 1 Arduino Nano
- 5 100KΩ resistors
- 1 3.7V LiPo Battery
- 1 DC voltage boost converter
- 1 TM1637 LED digit counter
- 5 Piezo ceramic wafer plates
- 1 push-button

I took a deep dive into piezoelectricity several months prior to this project, and I was excited to finally have an applied project for this fascinating phenomenon. I will be using manufactured piezoelectric ceramic wafers instead of quartz crystals, but the piezoelectric process is essentially the same.
### Piezoelectricity - Quartz
Piezoelectricity occurs when physical pressure is converted to an electric charge. Quartz is a beautiful example of piezoelecricity: when a precisely angled cut of quartz is struck, it releases voltage. One interesting quality of quartz is that every time it is struck with the same force, it releases the same voltage every time. This is why quartz is used in elecronic oscillators, clocks, and watches. 

![Silicon Dioxide](/assets/files/bar-mitzvah/silicon-dioxide.gif){:.centered}
*This is how silicon dioxide materials (e.g quartz) create DC voltage with pressure*

## Physical Routing

![Fritzing Model](/assets/files/bar-mitzvah/shield-bb.jpg){:.centered}

The Piezo wafer sensors are connected to the analog ports to provide different feedback for various pressures. I also attached a 100KΩ resistor to each wafer to prevent damage to the Nano. I used whatever large-load resistors were lying around, but I recommend 1MΩ for future projects.

I used [this](https://www.amazon.com/MakerFocus-Discharge-Integrated-Charging-Protection/dp/B07PZT3ZW2/) boost converter in my project because of its battery charging capabilities bundled with a pretty cool battery indicator. I desoldered the "key" button and bridged the connection with the push-button to allow turning on and prevent powering off.

## Code

This is the first completed project where I used a C++ class in a practical scenario. Although OOP wasn't necessary, it was interesting to complete. You can find the code [here](https://github.com/emorchy/piezo-shield).

## Images
<div class="row">
  <div class="column">
<div markdown="1">
![Exposed](/assets/files/bar-mitzvah/unconnected.jpg){:.centered}
*Sensor Placement*
</div>
  </div>
  <div class="column">
<div markdown="1">
![Covered](/assets/files/bar-mitzvah/cardboard.jpg){:.centered}
*Final Product*
</div>
  </div>
</div>

<div markdown="1">
<center>
  <iframe src="/assets/files/bar-mitzvah/livedemo.mp4" allowfullscreen></iframe>
  <p>
  <em>Shield Sensors Demo (2 candies thrown simultaneously)</em>
  </p>
</center>
</div>

## Final Thoughts
The shield detected a total of 44 candies during his service. My brother got recognition of having the coolest and most well thought out Bar Mitzvah candy blocker in the synagogue. Sure, other children had tennis raquets or fly swatters, but they all cower at the might of Daniel's mighty Shield!

Could I have used a better wiring system? Were the wire solder connections exposed? Could I have aesthetically made it much prettier and safer? Yes to all these questions. I had the idea to create an impact-sensor shield with a built in counter a week before the Bar Mitzvah began, and I managed to finish it the night before. I am amazed I could even finish on time, let alone it working as well as it did.
