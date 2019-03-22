---
layout: post
title: "Tutorial 1: Terminal UI"
date: 2019-03-7
description: "Emulating an old school terminal with HTML and CSS"
---

One of the key design elements to command-ui is the look and feel of the basic UI. The game is focused on the pilot of a spacecraft interacting with the ship systems and AI through an old school crt-like terminal. Capturing this
retro terminal feel was the first task that I took on as part of creating the game.

The game itself is written entirely in HTML, CSS, and Javascript. The terminal UI is accomplished purely with CSS.

To start I assign my "crt" class to the entire body of the HTML page.

<script src="https://gist.github.com/benjamib/4a8c128cecc2839cce38fa175760ce38.js"></script>

The "crt" class contians the following CSS.

<script src="https://gist.github.com/benjamib/0262d13f96b28d9d53fa5354962d6cff.js"></script>


The ".crt::after" creates a nearly black background positioned absolutely on the screen.

The ".crt::before" creates a repeating background image that is a linear gradient. The linear gradient is what adds the scan line effect to the text that makes it look like an old school crt display.

To add a little extra crt-iness to the dispaly, I added a CSS animation that adds misconvergence to the display. This is the effect of the different color channels not always lining up.
The effect is created by animating a text-shadow that isolates the RGB colors at different intensities and positions.

<script src="https://gist.github.com/benjamib/273783a944754c7f2ec596be1fca5a75.js"></script>

This CSS animation is added to the "crt" class.

<script src="https://gist.github.com/benjamib/5003c518453ea9cd498209f66c8cf5a9.js"></script>

This takes care of the basic styling for the page. The next step is to create a place to display the terminal output. To handle this I use a text area with some basic styling.

<script src="https://gist.github.com/benjamib/40d1f01a44188d73c75082d2bb76b945.js"></script>

The green text color is a vibrant retro terminal green and the font is a monospaced terminal-style font keeping with the overall design aesthetic. I also removed all borders and padding.

The final step is to create the input text box with the prompt.

<script src="https://gist.github.com/benjamib/7412b6b4444d0459e58fa73c200acdb0.js"></script>

The "command" class is very similar to the "output" class, but just contains different sizing.

<script src="https://gist.github.com/benjamib/6a7e51c80fdea0a50d7702ab4ce40a3a.js"></script>

The final result is a very cool looking retro terminal.

![alt text](https://benjamib.github.io/assets/Screenshot 2019-03-11 at 11.08.42 PM.png "Retro Terminal")
