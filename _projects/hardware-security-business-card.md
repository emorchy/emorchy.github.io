---
title: Hardware Security Business Card
date: 2026-04-29
description: Created a useful PCB business card for breaking out non-volatile memory chips and providing a hardware protocol reference
---

<div class="img-row">
  <figure>
    <img src="/assets/files/hardware-card/front_final.jpg" alt="Card Front">
    <figcaption><em>Front</em></figcaption>
  </figure>
  <figure>
    <img src="/assets/files/hardware-card/back_final.jpg" alt="Card Back">
    <figcaption><em>Back</em></figcaption>
  </figure>
</div>

# Overview

I distributed a stylish and useful PCB business card at three conferences for the following reasons:
- Selflessly: benefit the hardware security community
- Selflessly: inspire others as I have been inspired
- Selfishly: impress fellow hardware security folk
- Selfishly: prove technical competence in the hardware security industry
- Selfishly: earn job referrals
<!--excerpt-->

# Why (storytime)

I had the fortunate opportunity to visit three hardware security conferences, all occurring in the span of one month. As a soon-to-be graduate with a couple of years of penetration testing experience, I was eager to make a favorable impression on those who might get me connected to a decent company.

I was first inspired by a business card I saw during my first [DEF CON](https://defcon.org), where a man distributed a stack of black and silver PCBs with his name on them. The PCB had traces hidden by the silkscreen (the pretty printed layers sandwiching the copper layers) that had an interesting function of cycling a series of LEDs in a [Knight Rider](https://www.lucidinsider.com/wp-content/uploads/2022/04/kitt-knight-rider-lights.gif) fashion. He ran out of the preassembled PCBs that held the LEDs and other components, but I managed to get one of the unpopulated business cards. Despite the lack of components, the sleekness, weight, uniqueness, and durability of the business card made it easily my favorite out of the dozens of cards I received that conference. From there, I realized that I would one day make my own PCB business card.

There are several PCB business cards out there for people to shamelessly clone and modify as their own. At times, I was tempted to copy some enticing business cards myself. I later realized that in the niche world of hardware security, no PCB business cards publicly existed for me to rip off. So I set about creating one for my own purpose.

I first researched what others had done. I looked at [Hackaday](https://hackaday.com/tag/pcb-business-card/) for PCB business card ideas. I found the [DigiKey Ruler](https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/6174/DKS_PCB_RULER.pdf), which was also a PCB with a ton of useful electrical engineering information. I taught myself KiCad and familiarized myself with PCB art tutorials [here](https://www.instructables.com/A-Guide-Artistic-PCBs/) and [here](https://blog.wokwi.com/a-practical-guide-to-designing-pcb-art/).

# Hardware

I did not include any hardware components on the board. The rationale was twofold:
1. A business card placed into a wallet needs a slim form factor. Rather than deal with the headache of scouring DigiKey for [TSSOP](https://en.wikipedia.org/wiki/Thin_Shrink_Small_Outline_Package) components, I decided the slimmest option had no components at all.
2. 55% Chinese tariffs! I wanted cheap business cards. Fewer components = more boards.

Thus, the following materials are required to replicate the procedure:

- 1 computer (ThinkPad recommended)

# Design

The lack of components makes for an easier board design. I settled on the following:

- Standard business card dimensions (88x55mm) with a 2.75mm corner radius (fillet is fancy)
- 2-layer board
- 0.8mm thickness: max thickness I allowed myself. 0.6mm was much more expensive.
- Gold HASL: this was a hard decision. Silver is cheaper than gold, but I like the gold look better. Tariffs be damned, I refuse to diminish the style.
- Ruler: a handy ruler in your wallet is an incredible multipurpose tool.

# Front

The front of the card would contain my name, title, email, website, a QR code to the website, and cool artwork. It would also contain a compact inch and millimeter ruler so the card provides immediate utility.

I decided to create a [PCBite probe](https://pcbitekit.com) artwork, which is a staple in the hardware security community for probing data lines. I also added SOIC-8 chip PCB art that the PCBite would probe.

![PCBite Front](/assets/files/hardware-card/pcbite_chip.png){: .center style="width:75%;"}
<center><em>Front board revision 1 (PCBite artwork)</em></center>

I replaced the PCBite logo on the probe with a mesh grid (and a golden [glider](https://web.archive.org/web/20260211232028/www.catb.org/hacker-emblem/) on the inside). The wire connected to the probe reads my initials (EM) in a UART waveform. The interior of the chip art looks like a decapped chip with wire bonds and features real copper traces between through holes. The black, white, shiny gold, and less shiny gold come from combinations of three layers: front silkscreen, front solder mask, and copper layer 1.

I later scrapped the idea of a cool PCB artwork in favor of a sleek professional front, shoving all the fun to the back.

![Card Front](/assets/files/hardware-card/front_final.jpg){: .center style="width:75%;"}
<center><em>Front board final</em></center>

The final revision of the front contains a cleaner ratio of color, drawing the eye from left to right. The gold traces connecting the through holes give a subtle image of a quantum computer without being overtly eye-catching. The result appears professional with a hint of originality that leads to the back of the card.

# Back

After a few weeks of iterations, the back of the card would have the following uses:

- A breakout board for a standard 8-pin EEPROM/Flash [SOIC](https://en.wikipedia.org/wiki/Small_outline_integrated_circuit)
- A pinout reference for the EEPROM/Flash chips
- A waveform visual for the most common hardware protocols (UART, SPI, I2C)
- A handy baud rate guide

![Card Back](/assets/files/hardware-card/back_final.jpg){: .center style="width:75%;"}
<center><em>Back board final</em></center>

The back held all of the aforementioned features, but I believed I could go above and beyond. My business card acts as a breakout board with the following connections:
- SOIC-8 pads
- SPI/I2C pinout names (contain pads and are themselves pads)
- Large alligator-clip-sized pads on the bottom corner
- 1.27mm, 2.0mm, and 2.54mm headers

Hardware security engineers almost always look for non-volatile media to extract key material and firmware. 8-pin SOIC EEPROM/Flash chips serve as a standard for these non-volatile memory chips, and this business card provides six feasible methods of connecting to the chip.

# KiCad

I used KiCad for all PCB editing, Gerber generation, and artwork. Source and hardware files are available [here](https://github.com/emorchy/hardware-business-card).

<!-- Collapsible section for long extras (schematics, extra plots, raw output). -->
<details>
  <summary>Schematic</summary>
  <img src="/assets/files/hardware-card/schematic.png" alt="Schematic" class="center" style="width:100%;" />
</details>

<details>
  <summary>PCB Editor</summary>
  <img src="/assets/files/hardware-card/pcb_editor.png" alt="PCB Editor" class="center" style="width:100%;" />
</details>

# PCB Manufacturer

I looked around to find the cheapest PCB manufacturer that fit the specifications for my board. I highly recommend looking at [PCBShopper](https://pcbshopper.com/), which can filter, sort, and list the cheapest manufacturers fitting your PCB requirements.

At the time, the cheapest vendor fitting my requirements was [AIVON](https://www.aivon.com/).

Timeline:

- May 11th: Sent the order
- May 13th: Build finished and product shipped
- May 14th: Delivered

The manufacturer had fast shipping and a speedy build at no additional cost for the first order. Incredible service by AIVON.

## Price Per Board
For 30 cards, the original price was set at $52. AIVON had a promotion for free shipping and $30 off the first order, which brought the order down to $23.08, or $0.77 per board. After the tariff on the non-discounted price, I had to pay an additional $26.54 in shipping/importing, bringing my grand total to $49.62, or $1.65 per board.

<details>
  <summary>Invoices</summary>
  <img src="/assets/files/hardware-card/invoice_1.png" alt="Invoice" class="center" style="width:100%;" />
</details>

# Takeaways

## The Good

1. I had been designing a PCB business card for three years before finally putting cursor to CAD tool. I am glad to have a finished product.
2. The cards were a hit at the conferences! Several people asked if they could keep one, and most of them thanked me profusely when I said yes. This was a far cry from begging people in the industry to take my business card. Instead, the hardware security community recognized the value of a portable ruler/breakout board/protocol reference card. Many said they had the idea for a PCB business card, with some saying I inspired them to finally make one.
3. The business cards made for a great talking point. I showed the card to someone at a conference table, and it was subsequently passed around and admired. Everyone at the table was happy when I gave them each a business card.
4. I became increasingly selective about whom I gave my card to, and I knew that the hardware security people would keep it on their person. A hardware security engineer is a specialized role, and few tools provide portable utility for this specific role.
5. Success Story:

    ![Card Use](/assets/files/hardware-card/card_use.jpg){: .center style="width:75%;"}
    <center><em>Board used as a debugger</em></center>

    A person I met at the conference used my card to debug his DEF CON village badge.
6. I learned an incredible amount about PCB manufacturing, creating custom libraries and footprints, and going through the full process of idea to design to manufacturing to product. I also memorized KiCad hotkeys as if my productivity depended on it.

## The Bad

1. The gold HASL was fancy and added to the card's beauty, but switching to silver would have cut the price.
2. I spent a large amount of time on this project without a monetary profit. The conferences led to several job leads, and the business cards certainly sweetened the pot for some. However, the strongest leads came from people I've known for years who could already vouch for my ability without seeing the card. Rapport with colleagues and friends outclasses a business card.
3. The trace for pin 6 runs a bit too close to pin 5 under the SOIC footprint. It is easy to rip a pad when swapping chips, and there is sometimes a signal integrity issue between pins 5 and 6. Minor, but worth revisiting in a future revision.

## The Ugly

1. Feature creep is the silent killer of many of my projects. If it were not for the looming deadline of the three conferences, I would never have finished. Even then, I did not finish in time for the first conference, and the order arrived on the first day of the second conference. I need to do better at accepting that perfection is unattainable and knowing when to stop iterating.
2. Committing to a design on paper would have saved me much more time than the 50+ hours of iterating and tinkering on KiCad.
3. Verify DRC (Design Rule Check) before finishing object alignments. I adjusted everything too many times because of a single DRC violation. Ensure that the DRC in KiCad settings is the same as the PCB manufacturer specs.

![Card Front and Back](/assets/files/hardware-card/real_front_back.jpg){: .center style="width:75%;"}
<center><em>Physical business card</em></center>
